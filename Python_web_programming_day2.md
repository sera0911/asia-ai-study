{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Python_web_programming_day2.md",
      "provenance": [],
      "authorship_tag": "ABX9TyODGd8989SbpBh7UvumbgBT",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/sera0911/asia-ai-study/blob/main/Python_web_programming_day2.md\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "Ay_83L29nrsb"
      },
      "source": [
        "### django\n",
        "\n",
        "Static Pages   \n",
        "- Web Server는 파일 경로 이름을 받아 경로와 일치하는 file contents를 반환한다.  \n",
        "- 항상 동일한 페이지를 반환한다.\n",
        "- Ex) image, html, css, javascript 파일과 같이 컴퓨터에 저장되어 있는 파일들  \n",
        "\n",
        "\n",
        "Dynamic Pages   \n",
        "- 인자의 내용에 맞게 동적인 contents를 반환한다.\n",
        "- 즉, 웹 서버에 의해서 실행되는 프로그램을 통해서 만들어진 결과물 * Servlet: WAS 위에서 돌아가는 Java\n",
        "Program\n",
        "- 개발자는 Servlet에 doGet()을 구현한다.  \n",
        "\n",
        "- web 1.0 - 동기방식, 정적페이지 응답, full browsing   \n",
        "\n",
        "cgi - process, 동적으로 html생성 , container(jdk가 포함된 servlet/jsp 컨테이너), 요청마다 스레드 기반 실행   \n",
        "WAS - tamcat, jeus, webphere, weblogic   \n",
        "- web 2.0 - Ajax, 비동기방식, 부분 페이지 갱신  \n",
        "\n",
        "FrontEnd (Web 표준), RICH   \n",
        "BackEnd (web Framework)\n",
        "\n",
        "\n",
        "Web Server\n",
        "- 하드웨어 - Web 서버가 설치되어 있는 컴퓨터\n",
        "- 소프트웨어 - 웹 브라우저 클라이언트로부터 HTTP 요청을 받아 정적인 컨텐츠(.html .jpeg .css 등)를 제공하는 컴퓨터 프로그램\n",
        "- HTTP 프로토콜을 기반으로 하여 클라이언트(웹 브라우저 또는 웹 크롤러)의 요청을 서비스 하는 기능을 담당한다.\n",
        "- 정적인 컨텐츠 - WAS를 거치지 않고 바로 자원을 제공한다.\n",
        "- 동적인 컨텐츠 - 클라이언트의 요청(Request)을 WAS에 보내고, WAS가 처리한 결과를 클라이언트에게 전달(응답,\n",
        "Response)한다.\n",
        "- 클라이언트는 일반적으로 웹 브라우저를 의미한다.\n"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "NiD_U7KyrX21"
      },
      "source": [
        "#### Django Framework\n",
        "- 파이썬으로 작성된 웹 개발 프레임워크.\n",
        "- MTV 아키텍처를 따르고, ORM(Object Relational Mapper)이 프로젝트의 객체들을 데이터베이스 테이블과 매핑을 도와주어 복잡한 데이터 기반 웹 사이트 개발이 쉬워질 수 있다.\n",
        "- Instagram, Disqus, Mozilla, NASA 등이 Django로 개발되었다.\n",
        " 파이썬 기반 웹 프레임워크\n",
        "- 파이썬의 라이브러리를 사용할 수 있다.\n",
        "- 오픈소스\n",
        "- 기본적인 기능들을 미리 만들어 제공해 쉽고 빠르게 개발\n",
        "- Full Stack Framework : front, backend 등 서버가 필요로 하는 것을 모두 Django가 맡아서 함.\n",
        "- 수많은 만들어진 기능을 제공하지만 세세한 설정 변경이나 자세한 조정이 힘들다.\n",
        "- 모든 것이 Django ORM을 기반으로 한다.\n",
        "- 작업하는데 full system의 지식이 필요하다.  \n",
        "\n",
        "\n",
        "Django  \n",
        "1. 웹 서버에 요청이 오면 장고로 전달   \n",
        "2. 장고 urlresolver는 웹 페이지의 주소를 가져와 urls.py에서는 들어온 url의 end point를 구분하여 일치하는 패턴을 찾는다   \n",
        "3. 일치하는 패턴이 있으면, 장고는 해당 요청을 관련된 함수(view)에 넘겨준다 \n",
        "(해당 앱에서 다시 한 번 end point에 따라 url 패턴을 찾고, views.py에서 해당하는 class내에 함수를 호출)\n",
        "\n",
        "MVC(Model-View-Controller) 패턴\n",
        "\n",
        "- 모델(Model)은 애플리케이션의 정보(데이터)를 나타내며, 데이터베이스나 파일 등의 데이터 소스를 제어\n",
        "한다\n",
        "- 뷰(View)는 텍스트, 체크박스 항목 등과 같은 사용자 인터페이스 요소를 나타내고, 모델로부터 제공된 데\n",
        "이터를 반영하여 사용자에게 보여주게 되는 부분이다.\n",
        "- 컨트롤러(Controller)는 데이터와 비즈니스 로직 사이의 상호동작을 관리(사용자의 요청을 파악하여 그에\n",
        "맞는 데이터를 모델에 의뢰하고, 그것을 뷰에 반영하여 사용자에게 제공) 한다\n",
        "\n",
        "MTV 패턴  \n",
        "\n",
        "- MTV에서의 Model은 데이타를 표현하는데 사용되며, Python 클래스 형식으로 정의된다  \n",
        "Model은 하나의 모델 클래스는 DB에서 하나의 테이블로 표현된다.\n",
        "- MTV의 View는 HTTP Request를 받아 그 결과인 HTTP Response를 리턴하는 컴포넌트로서,  \n",
        "Model로부터 데이타를 읽거나 저장할 수 있으며,  \n",
        "Template을 호출하여 데이타를 UI 상에 표현하도록 할 수 있다.  \n",
        "- MTV의 Template은 Presentation Logic 만을 갖는데 HTML을 생성하는 것을 목적으로 하는 컴포넌트이다.\n",
        "템플릿(Template)은 사용자에게 보여지는 부분만을 담당한다.\n",
        "\n",
        "\n",
        "Django MTV 개발 방식  \n",
        "- 모델 - 테이블 정의   \n",
        "Python 클래스이며, django.db.models.Model 클래스를 상속받는 서브클래스이다.  \n",
        "- models.py 파일에 모델을 정의  \n",
        "\n",
        "Django App  \n",
        "- Django App은 Django 프로젝트 내에서 사용하는 “Python 패키지”이다\n",
        "- Django App 패키지 안에 독자적인 모델(model), 뷰(view), 템플릿(template), URL 매핑 등을 가지고 있으며, 하나의 Django 프로젝트는 모듈화된 여러 개의 앱들로 구성된다.\n",
        "\n",
        "Creating a project\n",
        "\n",
        "- 외부 mysite/ : 루트 디렉토리는 프로젝트의 컨테이너\n",
        "- manage.py: Django 프로젝트와 다양한 방식으로 상호 작용할 수 있는\n",
        "명령 줄 유틸리티\n",
        "- 내부 mysite/ : 디렉토리는 프로젝트의 실제 파이썬 패키지\n",
        "- mysite/settings.py: Django 프로젝트의 설정 / 구성\n",
        "- mysite/urls.py : Django 프로젝트의 URL 선언\n",
        "- mysite/asgi.py : ASGI 호환 웹 서버가 프로젝트를 제공하기위한 진입 점\n",
        "- mysite/wsgi.py: WSGI 호환 웹 서버가 프로젝트를 제공하기위한 진입 점\n",
        "- 'mysite.settings'설정을 사용하는 Django 버전 3.0http://127.0.0.1:8000/ 에서 개발 서버 시작\n",
        "- CONTROL-C로 서버 종료\n",
        "\n",
        "MTV 코딩 순서  \n",
        "1. 프로젝트 뼈대 만들기 : 프로젝트 및 앱 개발에 필요한 디렉토리와 파일 생성  \n",
        "2. 모델 코딩하기 : 테이블 관련 사항을 개발(models.py, admin.py 파일)  \n",
        "3. URLconf 코딩하기 : URL 및 뷰 매핑 관계를 정의 (urls.py 파일)  \n",
        "4. 뷰 코딩하기 : 애플리케이션 로직 개발(views.py 파일)  \n",
        "5. 템플릿 코딩하기 : 화면 UI 개발 (templates/디렉토리 하위의 *.html 파일들)   \n",
        "\n",
        "\n",
        "공통 모듈 구조  \n",
        "- Django 프로젝트 기본 설정 옵션은 settings.py 모듈 파일 하나로 설정한다.\n",
        "- settings.py 파일의 내용  \n",
        "• 데이터베이스 설정 : 디폴트로 SQLite3 데이터베이스 엔진을 사용하는 것을 지정  \n",
        "• 템플릿 설정 : TEMPLATES 항목으로 지정   \n",
        "• 지역 시각 및 다국어 설정 : 최초에는 세계표준(UTC)로 설정되어 있는데 , 한국 시간으로 변경해야 합니다.  \n",
        "• 애플리케이션의 등록 : 개발하는 앱, 프로젝트에 포함되는 애플리케이션들을 모두 설정 파일에 등록  \n",
        "• 정적 파일 설정 : STATIC_URL 등 관련 항목을 지정  \n",
        "• 미디어 파일 설정    \n",
        "• 루트 디렉토리를 포함한 각종 디렉토리의 위치, 로그의 형식, 디버그 모드, 보안 관련 사항 등 프로젝트 전반적인사항을 설정"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Tp8geeHPxQtf"
      },
      "source": [
        "#데이터베이스 설정\n",
        "DATABASES = {\n",
        "'default': {\n",
        "'ENGINE': 'django.db.backends.sqlite3',\n",
        "'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),\n",
        "}\n",
        "}"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "JqaEPgw5xTcr"
      },
      "source": [
        "#템플릿 설정\n",
        "TEMPLATES = [\n",
        "{\n",
        "'BACKEND': 'django.template.backends.django.DjangoTemplates',\n",
        "'DIRS': [os.path.join(BASE_DIR, 'templates')],\n",
        "'APP_DIRS': True,\n",
        "'OPTIONS': {\n",
        "'context_processors': [\n",
        "'django.template.context_processors.debug',\n",
        "'django.template.context_processors.request',\n",
        "'django.contrib.auth.context_processors.auth',\n",
        "'django.contrib.messages.context_processors.messages',\n",
        "],\n",
        "},\n",
        "},\n",
        "]"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "GEbVE4kaxXlu"
      },
      "source": [
        "#한국어로 설정 변경\n",
        "LANGUAGE_CODE = 'ko-kr'\n",
        "TIME_ZONE = 'Asia/Seoul'\n",
        "USE_I18N = True\n",
        "USE_L10N = True\n",
        "USE_TZ = True"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "H_OhPojaxo_N"
      },
      "source": [
        "#정적 파일 설정 - 기본 설정 값\n",
        "STATIC_URL = '/static/'"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Fzvbd5ikxtIE"
      },
      "source": [
        "#STATIC_URL 변수를 추가\n",
        "STATIC_ROOT = os.path.join(BASE_DIR, 'static')\n",
        "STATICFILES_DIRS = [\n",
        "os.path.join(BASE_DIR, 'static'),\n",
        "]"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "SraoxY2yxwmk"
      },
      "source": [
        "#미디어 파일 설정- 프로젝트 기본 설정값은 없으며 파일 업로드 기능 구현을 위해 다음 설정을 추가\n",
        "MEDIA_URL = '/media/'\n",
        "MEDIA_ROOT = os.path.join(BASE_DIR, 'media')"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "eT6D1GYjx1se"
      },
      "source": [
        "- runserver 테스트 서버 구동 시에 /media 경로를 올바로 찾지 못하는 문제가 발생한다. 따라서 URL 패턴 매칭을 해주는 다음 코드가 필요하다.(중요)"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "3ZQz_rGUx6iz"
      },
      "source": [
        "from django.conf.urls.static import static\n",
        "urlpatterns = [\n",
        "....\n",
        "]\n",
        "if settings.DEBUG:\n",
        "urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)"
      ],
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "1cRGMj8Dx9ed"
      },
      "source": [
        "애플리케이션 등록(urls.py)  \n",
        "- 앱을 생성한 경우 해당 앱 디렉토리 안에 기본 생성 파일  \n",
        "- 앱이름/app.py파일에 정의된 앱이름 config클래스가 config/settings.py에 인식하지 않으면"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "pp8GV2DK6QcG"
      },
      "source": [
        "질문 게시판 - 질문, 답변   \n",
        "DB구성,  \n",
        "질문, 답변 데이터 저장할 테이블 생성 - ORM 기능으로 처리  \n",
        "\n",
        "- 데이터를 관리하는 모델 생성을 위해서  \n",
        "장고 프레임워크에서 제공하는 기본 앱(admin, auth, contenttypes,sessions)의 저장소인 테이블을 생성하는 명령 수행  \n",
        "\n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py migrate  \n",
        "```\n",
        "- 장고 프레임워크에서 제공하는 기본 앱 정보 확인  \n",
        "프로젝트/ config/settings.py 파일에\n",
        "\n",
        "```\n",
        "INSTALLED_APPS = [  \n",
        "    'django.contrib.admin',  \n",
        "    'django.contrib.auth',  \n",
        "    'django.contrib.contenttypes',  \n",
        "    'django.contrib.sessions',  \n",
        "    'django.contrib.messages',  \n",
        "    'django.contrib.staticfiles',  \n",
        "]\n",
        "```\n",
        "- 모델 생성시에   \n",
        "\n",
        "질문 게시판의 질문 데이터 모델 생성 - subject(제목), content(내용), create_date(질문작성일자)    \n",
        "\n",
        "질문 게시판의 답변 데이터 모델 생성 - question(부모 object 참조), content(내용), create_date(답변작성일자)  \n",
        "\n",
        "- 모델은 앱에 종속되어 있기 때문에 반드시 장고 프레임워크에 앱을 등록해야 테이블 작업을 진행 할 수 있다  \n",
        "\n",
        "config/settings.py파일에 자동생성된 'first.apps.FirstConfig'를 등록합니다  \n",
        "```\n",
        "INSTALLED_APPS = [     \n",
        "    'first.apps.FirstConfig',  \n",
        "    'django.contrib.admin',    \n",
        "    'django.contrib.auth',    \n",
        "....  \n",
        "]  \n",
        "```\n",
        "\n",
        "\n",
        "\n"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "TVP0iPWls2VR"
      },
      "source": [
        "- 테이블 생성  \n",
        "\n",
        "모델이 생성되거나 변경된 경우 migrate 명령을 실행하려면 테이블 작업 파일이 필요하고, 테이블 작업 파일을 만들려면 makemigrations 명령을 먼저 실행해야 한다     \n",
        "테이블 작업 파일 생성    \n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py makemigrations  \n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py migrate  \n",
        "```\n",
        "sqlmigrate 도구를 사용해서 어떤 쿼리문이 실행되는지 확인  \n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py sqlmigrate first 0001  \n",
        "```\n",
        "- 장고 셸 실행  \n",
        "\n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py shell  \n",
        "from first.models import Question, Answer  \n",
        "from django.utils import timezone\n",
        "q = Question(subject='장고 사용자 앱 first의 주제는 무엇입니까?', content='first앱의 주제에 대해 알고 싶습니다.', create_date=timezone.now())  \n",
        "q.save()  \n",
        "q.id   \n",
        "q = Question(subject='ORM은 무엇입니까?', content='테이블과 클래스의 매핑관계 설정은 어떻게 이루어지나요?', create_date=timezone.now())    \n",
        "q.save()  \n",
        "q.id   \n",
        "Question.objects.all()\n",
        "```\n",
        "\n",
        "- 장고 프레임워크에 저장된 모델 데이터는 모델클래스명.objects를 사용해서 조회합니다  \n",
        "\n",
        "Question.objects.filter(id=1)  \n",
        "filter함수는 조건에 해당하는 데이터를 모두 찾아준다(반환 값은 리스트 형태의 QuerySet)  \n",
        "get함수는 단 하나의 레코드를 조회 결과로 반환한다  \n",
        "Question.objects.get(id=1)    \n",
        "Question.objects.get(id=10) #반드시 하나의 객체를 반환해야 하므로 Error 발생    \n",
        "Question.objects.filter(id=10)  #빈리스트 출력됨  "
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "0aGP_H8Ts9YH"
      },
      "source": [
        "- 제목으로 데이터 검색  \n",
        "\n",
        "```\n",
        "Question.objects.filter(subject__contains='ORM')\n",
        "```\n",
        "- 제목 수정  \n",
        "\n",
        "```\n",
        "q = Question.objects.get(id=2) \n",
        "  \n",
        "q.subject='장고 ORM 기능은 무엇인가요?'  \n",
        "q.save()  \n",
        "q  \n",
        "q=Question(subject='테스트', content='테스트', create_date=timezone.now())  \n",
        "q.save()  \n",
        "Question.objects.all()  \n",
        "q = Question.objects.get(id=3)   \n",
        "q.id \n",
        "q.delete()  \n",
        "q.save()  \n",
        "Question.objects.all()  \n",
        "```\n",
        "```\n",
        "q=Question.objects.get(id=1)  \n",
        "q  \n",
        "답변생성 (insert 수행됨)\n",
        "a = Answer(question=q, content=\"장고 프레임워크로 질문 게시판 파일럿 웹 앱 실습\", create_date=timezone.now())  \n",
        "a.save()  \n",
        "a.question  \n",
        "q.answer_set.all()  #질문과 답변을 모두 조회\n",
        "```\n",
        "\n",
        "- 모델 오류로 테이블 다시 생성하려면   \n",
        "반드시 db browser for sqlite 프로그램을 닫고 실행하는 것을 권장합니다  \n",
        "\n",
        "first/models.py 파일에 class 두 개 삭제 후  \n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py makemigrations  \n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py migrate   \n",
        "```"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "MeE7aVOAtDLz"
      },
      "source": [
        "first/models.py 파일에 class(Question, Answer) 다시 정의 한 후  \n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py makemigrations  \n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py migrate \n",
        "```\n",
        "\n",
        "-장고 shell 대신 개발 편의를 제공하는 장고 admin \n",
        "\n",
        "슈퍼 유저 생성하기  \n",
        "```\n",
        "(myweb) c:\\workspace\\project\\mysite>python manage.py createsuperuser  \n",
        "admin 아이디   \n",
        "12345678 비밀번호  \n",
        "admin@asiae.com 이메일  \n",
        "```\n",
        "\n",
        "http://127.0.0.1:8000/admin 으로 로그인해서 확인  \n",
        "\n",
        "\n",
        "장고 Admin에서 모델을 관리하려면 등록을 해야 합니다  \n",
        "admin.py파일\n",
        "```\n",
        "from django.contrib import admin\n",
        "from .models import Question\n",
        "\n",
        "admin.site.register(Question)\n",
        "```\n",
        "\n",
        "장고 Admin에서 데이터 검색 기능 추가하기  \n",
        "\n",
        "render함수는 context에 저장한 Question 모델 데이터 question_list를 frist/question_list 파일에 적용하여 HTML 코드로 변환한다  \n",
        "\n",
        "장고 프레임워크에서 Template 파일들은 프로젝트 폴더 아래 /templates/ 디렉토리 생성하고 저장함\n",
        "\n",
        "- 생성한 templates 디렉토리는 settings.py에서 등록해야 합니다\n",
        "\n",
        "```\n",
        "TEMPLATES = [   \n",
        "    {  \n",
        "        ...   \n",
        "        'DIRS': [ BASE_DIR / 'templates'],    \n",
        "        ...    \n",
        "            },   \n",
        "]    \n",
        "```\n",
        "\n",
        "- 템플릿 태그:  \n",
        "html 태그에는 반복 조건 태그가 없음므로 스크립트 영역을 선언하고 python언어로 조건, 제어 문장 기술한다   \n",
        "\n",
        "{% if 조건문1 %}\n",
        "  <p> 조건문1에 해당하는 경우 </p>\n",
        "{% elif 조건문2 %}\n",
        "  <p> 조건문2에 해당하는 경우 </p>  \n",
        "{% else %}\n",
        "  <p> 조건문1, 2에 모두 해당하지 않는 경우 </p>\n",
        "{% endif %}  \n",
        "\n",
        "{% for item in list %}  \n",
        "  <p> 순서 : {{forloop.counter }} </p>\n",
        "  <p> {{item}}  </p>  \n",
        "{% endfor %} \n",
        "\n",
        "forloop.counter - for문의 순서로 1부터 표시  \n",
        "forloop.counter0 - for문의 순서로 0부터 표시   \n",
        "forloop.first - for문의 첫번째 순서인 경우 True  \n",
        "forloop.last - for문의 마지막 순서인 경우 True  \n",
        "\n",
        "출력 템플릿 {{ 객체.속성 }}\n",
        "\n",
        "project아래 templates 폴더 생성 아래 first폴더 생성 아래 question_list.html 생성  \n",
        "```\n",
        "#question_list.html \n",
        "\n",
        "{% if question_list %}\n",
        "     <ul>\n",
        "        {% for question in question_list %}\n",
        "         <li> <a href=\"/first/{{ question.id }}/\">{{question.subject}}</a></li>\n",
        "        {% endfor %}\n",
        "     </ul>\n",
        "  {% else %}\n",
        "     <p> 질문이 없습니다. </p>\n",
        "\n",
        "  {% endif %}\n",
        "```\n",
        "http://127.0.0.1:8000/first/ 으로 확인  \n",
        "\n",
        "```\n",
        "#urls.py\n",
        "\n",
        "urlpatterns = [\n",
        "    path('', views.index),\n",
        "    path('<int:question_id>/', views.detail),\n",
        "\n",
        "]\n",
        "#int타입으로 수정, views.detail 함수사용\n",
        "```\n",
        "\n",
        "views.detail함수를 사용하기 위해 함수를 생성  \n",
        "```\n",
        "#views.py\n",
        "\n",
        "def detail(request, question_id) :\n",
        "    \"\"\"\n",
        "    질문 상세 내용 출력\n",
        "    \"\"\"\n",
        "    question = Question.objects.get(id=question_id)\n",
        "    context = {'question': question}\n",
        "    return render(request, 'first/question_detail.html', context)\n",
        "```\n",
        "\n",
        "first아래에 question_detail.html생성하기   \n",
        "```\n",
        "#question_detail.html   \n",
        "\n",
        "<h1> {{question.subject }} </h1>\n",
        "<div>\n",
        "  {{question.content}}\n",
        "</div>\n",
        "```\n",
        "http://127.0.0.1:8000/first/ 에서 제목을 클릭해서 내용이 뜨는 지 확인하기  \n",
        "\n",
        "first에서 제목 없는 페이지를 설정 시(ex.http://127.0.0.1:8000/first/10)=(id=10)  \n",
        "오류페이지를 더 간단하게 설정\n",
        "\n",
        "```\n",
        "#views.py\n",
        "\n",
        "def detail(request, question_id) :\n",
        "    \"\"\"\n",
        "    질문 상세 내용 출력\n",
        "    \"\"\"\n",
        "    #question = Question.objects.get(id=question_id)\n",
        "    question = get_object_or_404(Question, pk=question_id)\n",
        "    context = {'question': question}\n",
        "    return render(request, 'first/question_detail.html', context)\n",
        "``` \n",
        "\n",
        "\n",
        "config/settings.py의 DEBUG 항목이 True로 설정되어 있어 개발자에게 여러 정보를 알려주는 오류 화면이 나타난다.   \n",
        "개발 후 운영 및 서비스를 시작하면  DEBUG 항목을 False로 설정\n",
        "\n"
      ]
    }
  ]
}