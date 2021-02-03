# Django 인증 시스템

>Django에는 로그인 기능과 로그아웃 기능을 지원하는 앱과 미들웨어 프로그램이 내장되어 있다.

#### 관련 API

* **django contrib.auth 앱**에서 제공되는 User라는 모델 클래스를 통해서 회원을 가입하고 가입된 회원정보를 통해서 로그인과 로그아웃 기능을 간단하게 처리할 수 있다.

```python
from django.contrib import auth
from django.contrib.auth.models import User

# 회원 가입
User.objects.create_user(회원 정보를 키워드 아규먼트로 설정)

user = User.objects.create_user(username = usermail,
                               first_name = firstname,
                               last_name = lastname,
                               password = password)

# 회원 체크
auth.authenticate(username = 사용자 계정, password = 사용자 패스워드)
(리턴값)
회원이 아니면 - None
회원이면 - 해당 회원의 User 객체

# 로그인
auth.login(request, User)

# 로그아웃
auth.login(request)

# 로그인 여부 체크
request.user.is_authenticated
```

