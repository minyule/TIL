# Python 01. 데이터 & 제어문

1. ```python
   inp=int(input())
   for i in range(1, inp+1):
       print(i)
   ```

2. ```python
   inp=int(input())
   for i in range(inp, -1, -1):
       print(i)
   ```

3. ```python
   inp=int(input())
   j=0
   for i in range(1, inp+1):
       j+=i
       if j>10000:
           break
   print(j)
   ```