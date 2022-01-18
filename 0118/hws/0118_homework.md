# Python 02. 데이터 & 제어문 homework

1. Mutable : List, Set, Dictionary

   Immutable : String, Tuple

2. ```python
   ran=range(1, 51)
   ran=list(ran)
   ran=ran[0:51:2]
   print(ran)
   ```

3. ```python
   dic={"짱구": 5, "짱아": 3, "봉미선": 30}
   ```

4. ```python
   n = 5
   m = 9
   for i in range(m):
       for j in range(n):
           print("*", end="")
       print("")
   ```

5. ```python
   temp=36.5
   print("입실 불가") if temp >= 37.5 else print("입실 가능")
   ```

6. ```python
   scores = [80, 89, 99, 83]
   j=0
   for i in scores:
       j=j+i
   print(j/len(scores))
   ```

   