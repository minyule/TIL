# Python 05. 데이터 구조 및 활용 homework

1. ```python
   def count_vowels(words):
       print(words.count("a") + words.count("e") + words.count("i") + words.count("o") + words.count("u"))
   ```

​		.count() 메서드를 사용해서 a, e, i, o, u의 개수들을 더해서 출력.

2. (4) .strip(chr) 특정 문자 지정하지 않으면 공백 제거

3. ```python
   def only_square_area(list1, list2):
       max_area=[]
       for num_list1 in list1:
           for num_list2 in list2:
               if num_list2 == num_list1:
                   max_area.append(num_list1*num_list1)
       print (max_area)
   ```

​		값 같을 때 제곱값 리스트 추가하고 출력. 정사각형이므로..