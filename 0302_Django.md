# 0302

## Django 설정하기

- vscode terminal (bash)
  pip install django==3.2.12
  django-admin startproject firstpjt .
  python manage.py runserver
  (ctrl + url click -> roket check)

  python manage.py startapp articles
  (articles(application) 폴더 무더기 생김, 무조건 먼저)

  

- settings.py INSTALLED_APPS 안에
'articles',

- urls.py (article에서 views라는 함수를 가져옴)
from articles import views
- urlpatterns 안에 path('주소', 함수),
- index라는 url로 가면, views안에 있는 index 함수 실행
path('index/', views.index),

- views.py : 함수 작성
def index(request):
	return render(request, 'index.html')

- article안에 templates 폴더 > index.html 만들기
! 템플릿, html 작성

python manage.py runserver
로 실행, ctrl + url click

---------------------------------

