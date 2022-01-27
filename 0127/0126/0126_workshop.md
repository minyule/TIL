# Python 07. 객체 지향 프로그래밍 workshop

1. pip
   1. faker 라는 패키지를 설치하기 위함.
   2. 커맨드 창 (git bash)


2. Basir Usages

   1. faker 모듈의 Faker 변수를 사용하기 위해 가져온다.

3.  Localization

   1.  init
   2. self
   3. name

4.  Seeding the Generator

   1. #1 결과 : Jason Brown, #2 결과 : 이지후

      seed()는 정적 메소드

   2. #1 결과 : 이도윤, #2 결과 : 박승현

      seed_instance()는 인스턴스 메소드

   seed()에서 시드를 4321로 주었을 때, 여러 번 시도해도 동일한 값이 출력되고, 

   seed_instance()에도 시드를 4321로 주었지만, 시도할 때마다 다른 값이 출력되었다.

   seed()는 같은 입력에서 동일한 난수가 발생하는지 확인하는 용도로, 

   seed_instance()는 class와는 무관하게 랜덤한 값을 만드는 용도로 사용 가능하다.