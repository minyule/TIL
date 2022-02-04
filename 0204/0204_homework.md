# Web 02. HTML & CSS homework

1. Semantic Tag

   header, section, footer

2. input Tag

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Document</title>
   </head>
   <body>
     
     <form action="">
       
       <label for="username">USERNAME : </label>
       <input type="text" id="username" 
       placeholder="아이디를 입력 해 주세요.">
       <br>
   
       <label for="pwd">PWD : </label>
       <input type="password" id="pwd" >
   
       <input type="submit" value="로그인">
   
     </form>
   
   </body>
   </html>
   ```

3.  rem

4.  자손 결합자 : 밑에 있는 모든 요소들에 적용된다. 예시에서 div에 속한 모든 p에 적용된다. div 안의 다른 요소에 포함된 p에도 적용된다.

   자식 결합자: 바로 밑에 있는 요소에만 적용된다. 예시에서 div에 속한 p에 적용되지만 div 안의 다른 요소에 포함된 p는 적용되지 않는다.