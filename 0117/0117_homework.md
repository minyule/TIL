# Python 01. 데이터 & 제어문

1. 변수 이름으로 사용하면 안되는 단어

   False, None, True, and, as, assert, async, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield

2. ```python
   num1=0.1*3
   num2=0.3
   num1, num2=int(num1), int(num2)
   ```

3. ```python
   n = 5
   m = 9
   nTimes = "*" * n + "\n"
   nFinal = "*" * n
   print(nTimes * (m-1) + nFinal)
   ```

4. ```python
   print("\"파일은 c:\\Windows\\Users\\내문서\\Python에 저장이 되었습니다.\"\n나는 생각했다. \'cd를 써서 git bash로 들어가봐야지.\'")
   ```

5. ```python
   ans1 = (-b + (b * b - 4 * a * c) ** 0.5 ) / 2 * a
   ans2 = (-b - (b * b - 4 * a * c) ** 0.5 ) / 2 * a
   ```
