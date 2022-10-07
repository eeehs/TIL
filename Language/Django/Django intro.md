### 장고란?

---

Django는 Python을 사용하여 웹 사이트를 더 쉽게 만들 수 있는 **Python 프레임워크**입니다.

Django는 웹 애플리케이션 구축에 집중할 수 있도록 어려운 작업을 처리합니다.

Django는 **DRY(Don't Repeat Yourself)라는** 구성 요소의 재 사용성을 강조하며 로그인 시스템, 데이터베이스 연결 및 CRUD 작업(Create Read Update Delete)과 같은 즉시 사용할 수 있는 기능과 함께 제공됩니다.

### 장고가 어떻게 작동하는가?

---

Django는 MVT 디자인 패턴(Model View Template)을 따릅니다.

- Model
    - 표시하려는 데이터, 일반적으로 데이터베이스의 데이터
- View
    - 사용자의 요청에 따라 관련 템플릿 및 콘텐츠를 반환하는 요청 처리
- Template
    - 데이터를 표시하는 방법에 대한 로직과 함께 웹 페이지의 레이아웃을 포함하는 텍스트 파일(예: HTML 파일)

### Model

---

Model은 데이터베이스의 데이터를 제공

Django에서 데이터는 ORM(Object Relational Mapping)으로 전달되며, 이는 데이터베이스 작업을 더 쉽게 하기 위해 설계된 기술입니다. 

데이터베이스에서 데이터를 추출하는 가장 일반적인 방법은 SQL입니다. SQL의 한 가지 문제는 작업할 수 있으려면 데이터베이스 구조를 꽤 잘 이해해야 한다는 것입니다.

Django와 ORM을 사용하면 복잡한 SQL 문을 작성할 필요 없이 데이터베이스와 더 쉽게 통신할 수 있습니다.

**모델은 일반적으로 “models.py” 파일에 있습니다**

### View

---

View는 http 요청을 인수로 받아 관련 모델을 가져오고 템플릿으로 보낼 데이터를 찾아 최종 결과를 반환하는 함수 또는 메서드입니다.

**View는 일반적으로 views.py이라는 파일에 있습니다.**

### Template

---

template은 결과를 나타내는 방법을 설명하는 파일입니다.

Django는 레이아웃을 설명하기 위해 표준 HTML을 사용하지만 논리를 추가하기 위해 Django 태그를 사용

```html
<h1>My Homepage</h1>

<p>My name is {{ firstname }}.</p>
```

**애플리케이션의 Template은 Template 폴더에 있습니다.**

### URLs

---

jango는 또한 웹 사이트의 여러 페이지를 탐색하는 방법을 제공합니다.

사용자가 URL을 요청하면 Django는 URL을 보낼 뷰를 결정합니다.

이 작업은 urls.py이라는 파일에서 수행됩니다.

### Django의 작동 (MVT)

---

![mvt모델.PNG](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e8bb90f6-2331-4855-96a6-857c0b4e07da/mvt%EB%AA%A8%EB%8D%B8.png)

Django를 설치하고 처음 Django 웹 애플리케이션을 만든 후 브라우저가 URL을 요청하면 기본적으로 다음과 같이 됩니다.

1. Django는 URL을 수신하고 urls.py 파일을 확인한 후 URL과 일치하는 보기를 호출합니다.
2. views.py에 있는 View는 관련 모델을 확인합니다.
3. Model은 models.py 파일에서 가져옵니다.
4. 그런 다음 View에서는 데이터를 template folder에 지정된 template으로 보냅니다.
5. template에는 HTML 및 Django 태그가 포함되어 있으며, 데이터와 함께 완료된 HTML 콘텐츠를 브라우저로 반환합니다.