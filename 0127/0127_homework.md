# Python 08. 객체 지향 프로그래밍 homework

1. 

```python
circle = Circle(3, 2, 4)
print(circle.area(), circle.circumference())
```

> 28.259999999999998 18.84

넓이 : 28.26, 둘레 : 18.84

2. 상속 받기

```python
class Dog(Animal):
    def bark(self):
        print(f'{self.name}! 짖는다!')
class Bird(Animal):
    def fly(self):
        print(f'{self.name}! 푸드덕!')
```

> 멍멍이! 걷는다!
> 멍멍이! 짖는다!
> 구구! 걷는다!
> 구구! 먹는다!
> 구구! 푸드덕!

3. 

ZeroDivisionError : 0으로 수를 나눌 때 발생

NameError : 정의되지 않은 변수를 호출할 때 발생

TypeError : 타입이나 매개변수의 개수가 틀렸을 때 발생

IndexError : 존재하지 않는 index 값을 참조할 때 발생

KeyError : 존재하지 않는 key 값을 참조할 때 발생

ModuleNotFoundError : 존재하지 않는 Module을 불러올 때 발생

ImportError : 해당 라이브러리가 설치되지 않았을 때 발생