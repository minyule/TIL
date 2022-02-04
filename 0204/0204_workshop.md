# Web 02. HTML & CSS workshop

1. Semantic Tag

- semantic.css

```css
/* 아래 코드는 수정하지 마세요. */
body {
  font-family: Arial;
  width: 800px;
}

section {
  float: left;
  margin-left: 4px;
}

aside { 
  float: right;
  margin-right: 4px;
}

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}

/* 여기서부터 작성하세요. */
/* 모든 스타일 요소를 ***클래스***로 만들어 작성 후 사용합니다. */
.bg-lightgrey {
  background: lightgrey;
}
.bg-white{
  background: #ffffff;
}
/* 1. article 태그는 white로 나머지 시멘틱 태그는 lightgrey로 배경색을 바꿔주세요. */

.mar-pa-4{
  margin: 4px;
  padding: 4px;
}

/* 2. header, nav, footer 태그의 margin을 4px로 만들어주세요. */
/* 3. header, nav, footer 태그의 padding을 4px로 만들어주세요. */

.ver-mid{
  vertical-align: middle;
}
/* 4. h1 태그를 수평 중앙 정렬 시켜주세요. */

.wihe1{
  width: 490px;
  height: 300px;;
}
.wihe2{
  width: 280px;
  height: 300px;
}
/* 5. section 태그는 width 490px height 300px, 
   aside 태그는 width 280px height 300px로 만들어주세요.*/

.borders {
  border: 1px solid black;
  border-radius: 4px;
}
/* 6. 모든 semantic 태그의 border 두께를 1px, 실선, 검은색으로 만들어주세요. */
/* 7. 모든 semantic 태그의 border 모서리 반경을 4px로 만들어주세요. */

```

- semantic.html

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="semantic.css">
  <title>Layout Practice</title>
</head>
<body>
  
  <header class="bg-lightgrey mar-pa-4 borders">
    <h1 class="ver-mid">header</h1>
  </header>

  <nav class="bg-lightgrey mar-pa-4 borders">
    <h2>nav</h2>
  </nav>

  <div class="clearfix">

    <section class="bg-lightgrey wihe1 borders">
      <h2>section</h2>
      <article class="bg-white borders">
        <h3>article1</h3>
      </article>
      <article class="bg-white borders">
        <h3>article2</h3>
      </article>
    </section>

    <aside class="bg-lightgrey wihe2 borders">
      <h2>aside</h2>
    </aside>

  </div> 

  <footer class="bg-lightgrey mar-pa-4 borders">
    <h2>footer</h2>
  </footer>

</body>
</html>

```



