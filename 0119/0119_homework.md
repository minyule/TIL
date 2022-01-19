# Python 03. 함수

1. filter, divmod, abs, chr, hex, sum

2. ```python
   def get_middle_char(inp):
       if not len(inp)%2:
           print(inp[len(inp)//2-1]+inp[len(inp)//2])
       else:
           print(inp[len(inp)//2])
   ```

3. (4)

4. 10

5. ```python
   def my_avg(*inp):
       sum=0
       num=0
       for i in inp:
           sum=sum+i
           num=num+1
       print(sum/num)
   ```

   