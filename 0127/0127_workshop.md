# Python 08. 객체 지향 프로그래밍 workshop

## 도형 만들기

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

class Rectangle:
    def __init__(self, p1, p2):
        self.p1 = p1
        self.p2 = p2
    def get_area(self):
        return (self.p2.x - self.p1.x) * (self.p1.y - self.p2.y)
    def get_perimeter(self):
        width = self.p2.x - self.p1.x
        height = self.p1.y - self.p2.y
        return 2 *(width + height)
    def is_square(self):
        width = self.p2.x - self.p1.x
        height = self.p1.y - self.p2.y
        return width == height        

```

