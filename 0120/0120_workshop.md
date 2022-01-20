# Python 04. 함수

1. ```python
   def get_secret_word(inp):
       ans=&quot;&quot;
       for i in inp:
           ans=ans+chr(i)
       print(ans)`
   ```

2. ```python
   def get_secret_numbers(inp):
       ans=0
       for i in list(inp):
           ans=ans+ord(i)
       print(ans)
   ```

3. ```python
   def get_strong_word(inp1, inp2):
       inp1=ord(inp1)
       inp2=ord(inp2)
       if inp1>inp2:
           print(chr(inp1))
       elif inp2>inp1:
           print(chr(inp2))
   ```

   