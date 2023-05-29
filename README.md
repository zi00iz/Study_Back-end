# Study_Back-end
[동아리]Study-Back end

## 1주차-Web의 동작 원리: 클라이언트와 서버의 만남

### 1. Web의 등장

- WWW : Word Wide Web
- Web의 등장으로 누구나 프로그램을 대중에게 공개할 수 있게 됨.
- Web 2.0 (2010~현재)
    
    →일방향적으로 정보를 제공받던 사용자가 직접 정보를 생산하고 공유할 수 있게 됨.
    
- Web 3.0( 현재~)
    
    →데이터의 투명한 공개를 가장 큰 가치로 여기기 시작함
    
- 블록체인 기술의 등장
    
    느린 네트워크 처리 속도가 느림
    
    오픈소스 형태로 존재하는 것이 많아, 책임자 등 책임 소재가 불분명

### 2. 클라이언트와 서버

- 클라이언트(client): 브라우저를 통해서 요청(request)을 보내는 주체
- 서버(server): 클라이언트의 요청(request)을 수신해서 처리한 후 응답(response)을 보내는 주체

### 3. HTTP와 URL

- HTTP(HyperTextTransferProtocol): 웹브라우저에서 URL이라는 주소양식을 통해서 클라이언트와 서버가 통신하는 규칙.
- URL(Uniform Resource Locator): 인터넷상에 위차한 각종 자원들의 위치를 가르치는 주소 체계
- web상의 모든 자원들(영상, 사진, 텍스트 등)은 각자의 주소를 갖고 있다.
- 프로토콜(Protocol)
    
    → 통신 규칙 (http, https, ftp 등)
        
- 호스트(Host)
    
    → 서버의 주소
    
    → 호스트 네임, 루트 도메인이라고 지칭
        
- 경로(Path)
    
    → 호스트 내 서비스의 위치
    
    → 서비스 별로 분할됨( ex.검색, 회원 등)
        
- 쿼리 문자열(Query String)
    
    → ? 기호로 시작, &로 연결
    
    → 키/값 쌍으로 구성됨
    
### 4. 쿠키와 세션

- 쿠키: 서버에서 클라이언트로 보내져서 브라우저에 저장되는 아주 작은 크기의 데이터를 가르키는 말.
    
    → 키/값 구조로 되어 있고, 유효기간이 있음
    
    → 보안에 취약하다.
    
- 세션
    
    → 쿠키의 단점을 보완할 수 있음
    
    → 리소스 할당에 대해 절감할 수 있음
    

### 5. IP, Port, DNS

- 네트워크란?
    
    → 두 대 이상의 컴퓨터가 연결된 통신망
    
    → 거대 네트워크: INTERNET
    
- 스위치(switch): 동일한 네트워크에서 여러 컴퓨터가 통신을 가능하게 도와주는 장치
- 라우터(router): 다른 네트워크 간에 통신을 가능하게 함 (ex.공유기)

- **IP - Internet Protocol**
    
    : 컴퓨터 간 데이터를 주고받는 네트워크 계층의 규약
    
    → 데이터 전달에 필요한 ‘목적지 컴퓨터 정보’가 필요
    
- **IP 주소**
    
    : 네트워크에서 컴퓨터가 부여받는 고유한 주소
    
    →IP 주소의 실제 값은 2진수로 이루어져 있음.
    
    →하나의 공인 IP에서 수많은 사설 IP할당이 가능
    
    →공인 IP(Public IP)
    
    전체 인터넷 망에서 고유하게 식별 가능한 주소
    
    IPv4 체계에서 자원 부족
    
    →사설 IP(Private IP)
    
    가정의 LAN과 같은 네트워크에서 할당되는 주소
    
    컴퓨터에서 조회되는 IP
    
- 127.0.0.1
    
    → localhost : 자신의 컴퓨터를 의미하는 것
    

- **Port**
    
    :서비스를 구분하는 역할
    

- **DNS(Domain Name Server)**
    
    :URL을 해석하여 IP주소로 반환하는 서버
    
    →국가, 기업  등이 운영
    
    →전세계DNS는 연결되어 있다.
    
    →장애가 발생할 경우, 클라이언트가 각종 서비스에 접속할 ‘문’이 사라진 것과 마찬가지이므로 서비스를 이용할 수 없을 뿐더러 막대한 피해가 발생함.
    
## 2주차-Django 구조 및 작동 원리/Django CRUD API 구현
### ch13-1. DRF 설치 및 프로젝트 생성

1. pip install pipenv
2. pipenv shell
3. pipenv install djangorestframework
4. django-admin startproject DjangoApi (프로젝트 생성)
5. 파이썬 가상환경 활성화시키기

### ch13-2. Django App추가

1. python .\manage.py startapp products (앱 생성)
2. [settings.py](http://settings.py) 에 APPS에 연결해주기

### ch13-3. CORS 설정

1. pipenv install django-cors-headers
2. [settings.py](http://settings.py)에 middleware 에 추가해주기
3. [settings.py](http://settings.py)에 CORS_ORIGIN_ALLOW_ALL = True 추가

### ch14-1. 모델 및 마이그레이션

1. [models.py](http://models.py) 에 모델 class 정의하기
2. makemigrations 
3. migrate

### ch14-2. Serializer

:데이터 파일을 json화 하기 위한 작업

# 3주차 - 백엔드 개발 기초

- 클라이언: 주로 요청을 보내는 역할
- 서버: 응답을 하는 역할

- 개발자가 보는 웹 시스템의 흐름
    1. 요청 (ex. 로그인 버튼 클릭) → 서버
    2. 응답 (ex. 로그인 페이지 전송) → 페이지(html, css, js)
    3. 요청 (로그인 하기 클릭) → 서버
    4. 로그인 결과 응답(서버)

프레임워크

-소프트웨어 개발을 위한 기능, 구조의 틀을 제공

-시스템 흐름을 프레인워크가 제어함

-장점

1. 효율적: 이미 구현되어 있는 코드로 시간과 비용을 절약하여 생산성이 높다.
2. 품질 향상: 개발자들이 검증한 코드로 버그를 최소화 할 수 있음
3. 유지보수 용이: 체계적인 코드관리로 유지보수가 용이하고, 프레임워크 기준으로 개발 하기에 수월한 협업도 가능하다.

라이브러리

-소프트웨어 개발을 위한 기능을 제공

-시스템 흐름을 개발자가 제어함

ORM

-객체지향 언어와 관계형 데이터베이스를 연결해주는 기술

-Models, QuerySetAPI 등이 ORM에 포

Templates

-자체 템플릿 시스템으로 디자인과 로직을 분리하여 독립적 개발 가능

-HTML 파일을 분리하여 재사용, 체계적으로 관리 가능

-HTML 파일에 include, if, for 등 템플릿 언어를 사용 가능

Forms

-데이터의 유효성 검사

-구성하고자 하는 형태 렌더링

Authentication

-시스템 인증과 권한부여 기본 제공

-구성 요소: 사용자, 권한, 그룹
