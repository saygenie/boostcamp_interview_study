# OAuth란 무엇인가

OAuth는 사용자들이 아이디와 비밀번호를 입력하지 않고 웹 사이트나 웹 어플리케이션에서 다른 웹 어플리케이션으로 접근할 수 있도록 하는 인가 방식이다.

## 동작 원리

먼저 비유해서 말해보자면, 아이디와 비밀번호를 가지고 로그인하는 방식은 사원증을 가지고 회사에 들어가는 방식이다. 하지만 외부 손님이 올 경우에는 사원증을 가지고 출입하는 것이 아니라 방문증을 가지고 입장하게 된다. 여기서 생각해야할 점은 외부 손님 또한 믿을 수 있는 회사에 다녀야한다는 것이다.

![](https://upload.wikimedia.org/wikipedia/commons/3/32/OpenIDvs.Pseudo-AuthenticationusingOAuth.svg)

그림과 비교해보자면 안드로이드가 방문하고자 하는 회사, 구글이 외부 손님이 다니고 있는 회사이다.

## OAuth 2.0

OAuth 1.0은 웹 애플리케이션이 아닌 애플리케이션에서는 사용하기 곤란하다는 단점이 있었다. OAuth 2.0은 이를 보완하는 작업에 있다. (아직 최종안이 나오지 않았다.)

- 웹 애플리케이션이 아닌 애플리케이션 지원 강화
- 암호화가 필요 없음 HTTPS를 사용하고 HMAC을 사용하지 않는다.
- Siganature 단순화 정렬과 URL 인코딩이 필요 없다.
- Access Token 갱신 OAuth 1.0에서 Access Token을 받으면 Access Token을 계속 사용할 수 있었다. 트위터의 경우에는 Access Token을 만료시키지 않는다. OAuth 2.0에서는 보안 강화를 위해 Access Token의 Life-time을 지정할 수 있도록 했다.

### 이해관계자

- Resource Owner (사용자)
- Resource Server (예. 네이버, 페이스북)
- Client (예. 쇼핑몰)