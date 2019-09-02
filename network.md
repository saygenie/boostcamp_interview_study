# GET, POST 방식의 차이점을 설명하시오

## HTTP Request Methods
> [HTTP request methods - HTTP \| MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Methods)

### GET
GET 메소드는 특정 리소스의 표시를 요청합니다. GET을 사용하는 요청은 오직 데이터를 받기만 합니다.
![image](https://user-images.githubusercontent.com/42646264/64108879-0cdd8a00-cdb9-11e9-82de-e38dd41a5a25.png)


### HEAD
HEAD 메소드는 GET 메소드의 요청과 동일한 응답을 요구하지만, 응답 본문을 포함하지 않습니다.


### POST
POST 메소드는 특정 리소스에 엔티티를 제출할 때 쓰입니다. 이는 종종 서버의 상태의 변화나 부작용을 일으킵니다.
![image](https://user-images.githubusercontent.com/42646264/64108913-1ff05a00-cdb9-11e9-9ad1-39a4f5f09131.png)


### PUT
PUT 메소드는 목적 리소스 모든 현재 표시를 요청 payload로 바꿉니다.

### DELETE
DELETE 메소드는 특정 리소스를 삭제합니다.

### CONNECT
CONNECT 메소드는 목적 리소스로 식별되는 서버로의 터널을 맺습니다.

### OPTIONS
OPTIONS 메소드는 목적 리소스의 통신을 설정하는 데 쓰입니다.

### TRACE
TRACE 메소드는 목적 리소스의 경로를 따라 메시지 loop-back 테스트를 합니다.

### PATCH
PATCH 메소드는 리소스의 부분만을 수정하는 데 쓰입니다.

## 답변
> GET은 리소스를 클라이언트로 가져다 달라는 것을 뜻하며, POST는 데이터가 서버로 들어가야 함을 의미(리소스를 새로 만들거나 수정하기 위해, 또는 클라이언트로 돌려 보낼 임시 문서를 생성하기 위해)합니다.

클라이언트와 서버가 통신을 하는 방법은 여러가지가 있습니다. 그중에서 `http`를 사용해서 클라이언트가 서버에게 '요청'하고 서버가 클라이언트에게 '응답'하는 경우가 많습니다. 클라이언트가 요청할 때 사용하는 방식들 중 하나가 `GET`과 `POST`입니다.
표면적으로 볼 때 `GET`방식은 url 뒤에 `?`를 붙이고 url과 쿼리를 함께 보내 사람들이 볼 수 있고, `POST`방식은 데이터가 `payload`안에 숨겨져 패킷 분석을 하지 않는 이상 확인할 수 없다는 차이점이 있습니다.
또한 용량제한도 `GET`방식 보다는 `POST`방식이 더 많은 데이터를 담을 수 있다는 차이점도 있습니다.
