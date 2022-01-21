# Project 01. Python을 활용한 데이터 수집 I

## 이번 pjt를 통해 배운 내용

- dictionary의 일부를 변환하기.
- python 코드로 json 파일을 입력받아 오는 방법.

## A. 제공되는 영화 데이터의 주요내용 수집

- 요구사항 : 제시된 키에 해당하는 정보를 데이터에서 가져오기.

- 결과

  - 문제 접근 방법 및 코드 설명

    - 코드
  
    ```python
    def movie_info(movie):
        dic={}
        # make Keys list
        list_key=["genre_ids", "id","overview", "poster_path", "title", "vote_average"]
        # add items in dic
        for i in list_key:
            dic[i] = movie[i]
        return dic
    ```
  
    - 결과값
  
    > {'genre_ids': [18, 80],
    >  'id': 278,
    >  'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
    >              '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
    >              '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 '
    >              '세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 '
    >              '이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...',
    >  'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
    >  'title': '쇼생크 탈출',
    >  'vote_average': 8.7}
  
  - 문제에서 어려웠던 점
  
    - 예시에는 genre_ids의 값이 [80, 18]로 나오는데 input을 그대로 출력해도 [18, 80]라고 나온다. 자동으로 정렬이 되는걸까? 리스트를 자동으로 정렬하지 않으려면 어떻게 해야할까?
    - JSON이라는 파일에서 input을 가져오라는 말이 무엇일까.. 설명만 읽고는 내적 고민을 많이하게 되었다. 다행히 이번 문제에서는 기본 코드가 주어졌지만 파일끼리 연결하는 걸 내가 직접 할 수 있을까? -> 한 것 같다! (E번을 푼 내가 과거의 나에게)
    - dictionary 구조를 불러오는게 익숙하지 않다. key와 value가 있어서 둘 다 고려하느라 기본 문법을 외우기가 헷갈린다. 주말에 외워야겠다.
    - 코드를 실행할 때 다른 파일을 찾지 못했다는 에러가 났다. 며칠 전부터 이 문제로 고민하고 있었는데 다행히 다른 친구가 질문해서 이유를 알아냈다. 파일 빈 곳에 우클릭을 해서 code를 열어야 하는 것이었다.
  
  - 내가 생각하는 이 문제의 포인트
  
    - dictionary 다루기에 익숙해지는 것
    - 다른 파일의 정보를 가져오는 것에 대해 겁먹지 않기

    

## B. 제공되는 영화 데이터의 주요내용 수정

- 요구사항 : genre_ids를 genre_names로 바꿔서 반환하는 함수 만들기

- 결과

  - 문제 접근 방법 및 코드 설명
    - movie.json의 id로 genre_json에서 names를 찾아서 바꾸기
    - 코드
    
    ```python
    def movie_info(movie, genres):
    #----A---------------------------------------------
        dic={}
        # make Keys list
        list_key=["genre_ids", "id","overview", "poster_path", "title", "vote_average"]
        # add items in dic
        for i in list_key:
            dic[i] = movie[i]
    #-------------------------------------------------    
        # 쇼생크 탈출의 genre_names에 들어갈 value 만듦
        list_genre=[]
        for i in genres:
            if i["id"] in dic["genre_ids"]:
                list_genre.append(i["name"])
    
        #dic에 genre_names의 key와 value 추가
        dic["genre_names"] = list_genre
    
        #dic에서 genre_ids 제거
        del dic["genre_ids"]
    
        return(dic)
    ```
    
    - 결과값
    
    > {'genre_names': ['Crime', 'Drama'],
    > 'id': 278,
    > 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
    >             '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
    >             '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 '
    >             '세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 '
    >             '이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...',
    > 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
    > 'title': '쇼생크 탈출',
    > 'vote_average': 8.7}
  
  - 문제에서 어려웠던 점
    - 딕셔너리의 항목을 '바꾼다' 라고만 생각하니 어떻게 해야할지 몰라서 헤맸다. '바꾼다'를 '필요한 항목을 추가한다' -> '필요없는 항목을 제거한다'라고 나누어서 생각하니 해결되었다.
    - 딕셔너리에서 자동으로 key를 기준으로 정렬이 되는줄 모르고 한참 헤맸다. 순서도 맞히고 싶어서 key의 리스트를 만드는 등 많이 헤맸지만... 나중에야 정렬이 된다는 것을 알게 되었다.
    
  - 내가 생각하는 이 문제의 포인트
    - '바꾼다'라는 것을 '필요한 항목 추가' -> '필요없는 항목 제거'로 절차를 나누어서 생각하기
    
    

## C. 다중 데이터 분석 및 수정

- 요구사항 : 모든 항목에 대하여 A, B단계에서 만들었던 함수 사용하기

- 결과

  - 문제 접근 방법 및 코드 설명

    - 코드
  
    ```python
    def movie_info(movies, genres):
        dic_about_all_movie=[]
        for j in movies:
            #----A---------------------------------------------
            dic={}
            # make Keys list
            list_key=["genre_ids", "id","overview", "poster_path", "title", "vote_average"]
            # add items in dic
            for i in list_key:
                dic[i] = j[i]
            #---B----------------------------------------------    
            # 쇼생크 탈출의 genre_names에 들어갈 value 만듦
            list_genre=[]
            for i in genres:
                if i["id"] in dic["genre_ids"]:
                    list_genre.append(i["name"])
    
            #dic에 genre_names의 key와 value 추가
            dic["genre_names"] = list_genre
    
            #dic에서 genre_ids 제거
            del dic["genre_ids"]
            dic_about_all_movie.append(dic)
            #------------------------------
        return(dic_about_all_movie)
    ```
  
    - 결과값
  
    > [{'genre_names': ['Crime', 'Drama'],
    > 'id': 278,
    > 'overview': '촉망받는 은행 간부 앤디 듀프레인은 아내와 그녀의 정부를 살해했다는 누명을 쓴다. 주변의 증언과 살해 현장의 '
    >             '그럴듯한 증거들로 그는 종신형을 선고받고 악질범들만 수용한다는 지옥같은 교도소 쇼생크로 향한다. 인간 말종 '
    >             '쓰레기들만 모인 그곳에서 그는 이루 말할 수 없는 억압과 짐승보다 못한 취급을 당한다. 그러던 어느 날, 간수의 '
    >             '세금을 면제받게 해 준 덕분에 그는 일약 교도소의 비공식 회계사로 일하게 된다. 그 와중에 교도소 소장은 죄수들을 '
    >             '이리저리 부리면서 검은 돈을 긁어 모으고 앤디는 이 돈을 세탁하여 불려주면서 그의 돈을 관리하는데...',
    > 'poster_path': '/3hO6DIGRBaJQj2NLEYBMwpcz88D.jpg',
    > 'title': '쇼생크 탈출',
    > 'vote_average': 8.7},
    >
    > #-----(생략)------
    >
    > ]
  
  - 문제에서 어려웠던 점
  
    - 단지 이전에 사용했던 코드를 가져오기만 하는 것이었다.
    - 코드가 길어지니까 변수가 어떤 것을 나타내는지 헷갈리기 시작했다.
    - 원래 변수 이름으로 낙타 모양이 익숙해서 그걸로 작성했었는데 뱀 모양으로 하다보니까 뱀 모양도 읽기 쉬운 것 같다.
  
  - 내가 생각하는 이 문제의 포인트
  
    - 변수 이름의 중요성
    
    

## D. 알고리즘을 통한 데이터 출력

- 요구사항 : 수익정보(revenue)를 이용하여 가장 높은 수익을 낸 영화의 제목 출력

- 결과

  - 문제 접근 방법 및 코드 설명

    - 코드
  
    ```python
    def max_revenue(movies):
        # movies의 모든 ids를 list로
        list_of_ids=[]
        for movies_kid in movies:
            list_of_ids.append(movies_kid["id"])
    
        # json 파일을 열고, 해당 파일에서 revenue를 갖고온다.(모든 파일에 대해서 시행) -> 모든 영화의 revenue로 이루어진 list 작성
        list_of_revenue=[]
        for movie_id in list_of_ids:
            json_open = open("data/movies/" + str(movie_id) + ".json", encoding="UTF8")
            data = json.load(json_open)
            list_of_revenue.append(data["revenue"])
    
        # 최대 수익을 내는 영화의 위치를 list_of_revenue에서 찾아서 list_of_ids에서 찾고
        index_of_max_revenue = list_of_revenue.index(max(list_of_revenue))
    
        # list_of_ids에서 찾은 값으로 해당 파일을 열어서 영화 제목 출력
        json_open = open("data/movies/" + str(list_of_ids[index_of_max_revenue]) + ".json", encoding="UTF8")
        data = json.load(json_open)
        return(data["title"])
    ```
  
    -  결과값
  
    > 반지의 제왕: 왕의 귀환
  
  - 내가 생각하는 이 문제의 포인트
  
    - json 파일을 파이썬 내부에서 읽어야 하는게 맞는 것 같은데 진짜로 해야하는 건지 의문이 들었다. 나는 못할 것이라는 생각이 지배적이었기 때문에.
    - json 파일을 여는 문법. 직접 해보는 것이 처음이어서 익숙치 않았다. 문법을 안 이후로는 청산유수처럼 해결되었다.
  
  - 내가 생각하는 이 문제의 포인트
  
    - python 코드를 통해 json 파일을 열고 데이터를 입력받기.
    - 변수는 점점 많아지고 변수의 이름과 주석이 매우 중요해졌다.
  
    

## E. 알고리즘을 통한 데이터 출력

- 요구사항 : 개봉일 정보(release_date)를 이용하여 12월에 개봉한 영화의 제목을 리스트로 출력

- 결과

  - 문제 접근 방법 및 코드 설명

    - 코드
  
    ```python
    def dec_movies(movies):
        # movies의 모든 ids를 list로
        list_of_ids=[]
        for movies_kid in movies:
            list_of_ids.append(movies_kid["id"])
    
        # json 파일을 list_of_ids를 통해 열고
        release_month_12 = []
        for movie_id in list_of_ids:
            json_open = open("data/movies/" + str(movie_id) + ".json", encoding="UTF8")
            data = json.load(json_open)
        # release_date의 월 부분이 12인지 확인한다.
        # 맞으면 release_month_12 리스트에 추가
            if data["release_date"][5:7] == "12":
                release_month_12.append(data["title"])
        return(release_month_12)
    ```
  
    - 결과값
  
    > ['그린 마일', '인생은 아름다워', '반지의 제왕: 왕의 귀환', '스파이더맨: 뉴 유니버스']
  
  - 문제에서 어려웠던 점
  
    - D번을 푼 이후라 오히려 쉬운 부분이었다.
    - 좀 아쉬운 부분은 날짜 형식을 입력받아서 월 부분만 받는 함수가 있지 않았을까 싶은 것. 문자열의 인덱스로 월 부분을 찾았는데 input 형식이 달라질까봐 약간 불안하다. 혹시나 해서 찾아보니 calendar 모듈에서 해당 기능을 지원하는 듯 하다.
  
  
  - 내가 생각하는 이 문제의 포인트
    - 리스트로 정보를 찾아서 리스트 작성하기



## 후기

- JSON 파일 불러오기를 직접 알아볼 수 있어서 좋았다. 몇 번 시도했는데 계속 이유를 모르겠는 오류가 나서 좀 슬펐다. 교수님께서 주신 힌트와 오류 문장을 잘 읽고서 오류의 이유를 알아냈고 해결했다! 눈물이 날 정도로 기뻤다. 패배주의가 생각의 밑바탕이 되어있는 것 같다. 이러한 생각을 바꿔야 한다고 오랫동안 되뇌고 있지만 쉽지가 않다. 이러한 성취를 몇 번 더 이루다보면 좀 달라질까.
- 원래 변수 이름을 아무 생각 없이 짓는 편이었다. 이번 프로젝트에서 비슷한 이름이 많이 나오고(movie, movies 처럼..) 변수들이 많아지니 구분하고 기억하기가 어려워졌다. 다~행히 많이 진행하기 전에 변수 이름들을 싹 고쳤다. 기존에 사용하던 낙타모양이랑 주어지는 코드의 뱀모양이랑 섞이니까 구분하기가 너무 어려워져서 낙타들도 다 뱀들로 바꿔버렸다. _ 입력하기가 귀찮았는데 막상 또 쓰다보니까 익숙해졌다. 변수 이름은 중요하구나.
- 주석도 완전 잘게잘게 나누어서 쓰니까 코드를 변형해서 활용하기가 용이했다.
- 2인 1조로 진행했었는데, 내 코드를 남에게 설명하기가 너무 어려웠다. 오랜만에 남에게 말을 하니까 더 떨리기도 했다. 말을 조리있게, 논리적으로, 듣기 쉽게 하도록 연습해야겠다.
- 원하는 결과가 나왔을 때는 매우 기뻤다. 한 번에 코드가 오류없이 실행되었을 때는 이게 제대로 돌아가는게 진짜 맞나? 싶어서 파일을 일일이 확인해봤다. 심지어 다시 중간 과정을 output으로 보기도 했다.
- 평소에 손도 머리도 느려서 나만 뒤쳐지면 어떡하지 걱정을 했다. B번을 풀 때는 뱅뱅 돌고 헤매서 더 시간이 걸렸었다. 다행히 그렇게 늦지 않게 프로젝트를 끝내서 다행이다. 
- 과정 중간중간마다 해설을 쓰고 정리하고, 문제 시작 전에 무엇을 요구하는지 파악하니까 더 체계적으로 정리되어서 좋았다. 그 순간순간 내가 무슨 생각을 했는지를 기록하니 내가 이 짧은 시간 안에 발전하는게 느껴져서 더 재미있었다.



2022.01.21 18:20
