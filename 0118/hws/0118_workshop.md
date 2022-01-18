# Python 02. 데이터 & 제어문 workshop

1. ```python
   inp = int(input())
   for i in range(1, inp + 1):
       if inp == i:
           print(i)
       elif inp%i == 0:
           print(i, end = " ")
   ```

2. ```python
   numbers=[85, 72, 38, 80, 69, 65, 68, 96, 22, 49, 67, 51, 61, 63, 87, 66, 24, 80, 83, 71, 60, 64, 52, 90, 60, 49, 31, 23, 99, 94, 11, 25, 24]
   numbers=sorted(numbers)
   numbers=numbers[len(numbers)//2]
   print(numbers)
   ```

3.  ```python
    inp=int(input())
    for i in range(1, inp+1):
        print(' '.join (map(str,range(1, i+1))))
    ```

   