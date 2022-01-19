# Python 03. 함수

1. ```python
   def list_sum(*inp):
       ans=0
       for i in range(0, len(inp[0])):
           ans=ans+inp[0][i]
       print(ans)
   
   list_sum([1, 2, 3, 4, 5])
   ```

2. ```python
   def dict_list_sum(inp):
       ans=0
       for i in inp:
           ans=ans+i.get('age')
       print(ans)
   ```

3. ```python
   def all_list_sum(inp):
       ans=0
       for i in inp:
           for j in i:
               ans=ans+j
       print(ans)
   ```

   