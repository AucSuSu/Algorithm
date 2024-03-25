# REST API
- REST: Representational State Transfer의 약자 -> 소프트웨어 프로그램 아키텍처의 한 형식
- 구체적인 개념
  - 자원 기반 구조 설계의 중심에 resource가 있고, http mehtod를 통해 resource를 처리하도록 설계된 아키텍처
  - 웹의 모든 자원에 고유한 ID인 HTTP URI(예: /mypage/1)를 부여하여 자원을 구분

```
- API: Application(고유의 기능을 가진 모든 sw) Programming Interface(두 애플리케이션 간의 서비스 계약)의 줄임말로 요청과 응답을 사용하여 두 애플리케이션이 통신하는 방법
- resource: 특정 애플리케이션이 가진 데이터
- CRUD: create(POST), read(GET), update(PUT: 전체 수정/PATCH: 부분 수정), delete를 의미, REST API에서 method라고 불린다
```



## REST의 구성
- **자원(Resource)**: URL로 모든 자원이 구별된다.
- **자원에 대한 행위(Verb)**: 자원에 대한 행위를 표시하기 위해 Http Method(GET, POST, DELETE, PUT, PATCH) 사용
- **표현(Representations)**: 클라이언트에서 자원의 상태에 대한 조작을 요청하면 서버가 이에 적절한 응답을 보낸다.(주로 JSON 형식으로)

<img width="683" alt="image" src="https://github.com/AucSuSu/CS-study/assets/75782242/5f143631-df55-499e-98c6-062d3017af69">



## REST의 특징
1. 클라이언트/서버 구조: 클라이언트는 사용자와 관련된 처리, 서버는 REST API 제공 -> 각자의 역할이 확실히 구분
2. Stateless(무상태성): 서버에서 어떤 작업을 하기 위해 상태 정보를 저장할 필요 X, 요청이 들어오는 것에 한해서만 처리하면 됨
3. Cacheable(캐시 처리 가능)
4. 자체 표현 구조: JSON과 같은 포맷을 통해 직관적으로 이해할 수 있고, REST API만으로 요청이 어떤 행위를 하는지 알 수 O
5. 유니폼 인터페이스: HTTP 표준만 따르면 모든 플랫폼에서 사용 가능 -> 특정 언어나 기술에 종속 X
6. Layered System(계층화)



## REST API 설계 시 고려사항
1. URI는 동사보다 **명사**, 대문자보다 **소문자**, 언더바(_)보다 **하이픈(-)**
```
😠 : http://byeoljari.com/Running/good_crew
👼 : http://byeoljari.com/run/good-crew
```
2. 마지막에 슬래시(/) 포함 X
```
😠 : http://byeoljari.com/run/
👼 : http://byeoljari.com/run
```
3. 파일 확장자 포함 X
```
😠 : http://byeoljari.com/photo.jpg
👼 : http://byeoljari.com/photo
```
4. 행위 포함 X (= Http Method 포함 X)
```
😠 : http://byeoljari.com/delete-photo/1
👼 : http://byeoljari.com/photo/1
```



## 요청에 따른 응답코드 정리
- `200`: 클라이언트 요청 정상 수행(응답에 대한 메시지 포함)
- `201`: 리소스 생성 요청에 대해 정상 처리
- `202`: 리소스 생성 요청이 비동기적으로 처리
- `204`: 클라이언트 요청 정상 수행(응답에 대한 메시지 미포함, 보통 삭제 요청)
- `400`: 클라이언트 요청이 부적절(부적절한 이유 응답 Body에 넣어줘야 함)
- `401`: 클라이언트가 인증되지 않은 상태에서 보호된 리소스 요청할 때 사용
- `403`: 클라이언트가 인증상태와 부관하게 응답하고 싶지 않은 리소스 요청할 때
- `404`: 클라이언트가 요청한 리소스가 존재하지 않을 때
- `405`: 클라이언트가 불가능한 메소드를 사용했을 때



# 면접 질문: Rest API에 대해서 설명해보시오.
```
REST란 Representational State Transfer의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것을 의미합니다.
Http URI로 자원을 명시하고, HTTP Method(GET,POST,PUT,DELETE,PATCH)로 자원의 상태를 주고 받는 방식을 말합니다.
즉, 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것이다.
```



## References
- https://velog.io/@somday/RESTful-API-%EC%9D%B4%EB%9E%80
- https://khj93.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-REST-API%EB%9E%80-REST-RESTful%EC%9D%B4%EB%9E%80
- 
