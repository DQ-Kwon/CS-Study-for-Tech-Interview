# CS Study - Network

<!-- prettier-ignore -->
|<- 이전 | 현재 | 다음 ->|
|:---:|:---:|:---:|
|[NAT와 포트포워딩](network-nat-port_forwarding)|HTTP 프로토콜|[-](./)|

<br/>

# 9. HTTP 프로토콜

## ❓ HTTP와 HTTPS의 차이에 대해 설명하세요.

### HTTP(Hyper Text Transfer Protocol)

서버/클라이언트 모델을 따라 데이터를 주고 받기 위한 프로토콜  
HTTP는 인터넷에서 하이퍼텍스트를 교환하기 위한 통신 규약으로, 80번 포트를 사용  
HTTP 서버가 80번 포트에서 요청을 대기하고, 클라이언트는 80번 포트로 요청을 보냄  
<br/>

### HTTPS(HTTP over Secure Socket Layer)

HTTP over TLS, HTTP over SSL, HTTP Secure 등으로 불리는 HTTPS는 HTTP에 데이터 암호화가 추가된 프로토콜이다. HTTPS는 HTTP와 다르게 443번 포트를 사용하며, 네트워크 상에서 중간에 제3자가 정보를 볼 수 없도록 암호화를 지원하고 있다.

> ### SSL 인증서
>
> 사용자가 사이트에 제공하는 정보(데이터)를 암호화해줌.

<br/>

## ❓ HTTP의 GET 방식과 POST 방식을 비교해주세요.

### GET 방식 특징

- URL에 쿼리 스트링(데이터)을 붙여서 서버에 전송
- 데이터를 Header(헤더)에 포함하여 전송
  -URL에 정보들이 그대로 노출되기 때문에 POST 방식보다 상대적으로 보안에 취약
- 캐싱이 가능
- POST 방식보다 상대적으로 전송 속도가 빠름
- 전송하는 데이터양에 한계가 있음 (브라우저마다 GET 요청 길이 제한 존재)
- 브라우저 히스토리에 기록이 남음  
  <br/>

### POST 방식 특징

- 데이터들을 URL뒤에 붙여서 서버로 보내는 것이 아닌 Body에 담아서 전송
- 요청 헤더의 Content-Type에 콘텐츠 타입을 명시
- 데이터들이 URL에 노출되지 않기 때문에 GET 방식보다 상대적으로 보안적
- 데이터들을 Body에 담기 때문에 서버로 보내는 데이터의 양은 제한 없음
- URL에 데이터가 노출되지 않으므로 캐싱 불가
- 클라이언트에서 인코딩, 서버에서 디코딩
- 요청받는 시간제한 존재
- 브라우저 히스토리에 기록이 남지 않음  
  <br/>

## ❓ HTTP의 Statue Code의 종류는 어떻게 되나요?

<br/>

<!-- prettier-ignore -->
|코드|명칭|설명|
|---|---|---|
|1xx|Info|요청을 받았으며 프로세스를 계속 진행|
|2xx|OK|요청을 성공적으로 받았으며 인식했고 수용|
|3xx|Redirection|요청 완료를 위해 추가 작업 조치가 필요|
|4xx|Bad Request|잘못된 문법으로 서버가 요청을 이해할 수 없음|
|404|Not Found|서버가 요청받은 리소스를 찾을 수 없음|
|5xx|Internal Server Error|서버가 명백히 유효한 요청에 대한 충족을 실패|
|502|Bad Gateway|서버가 게이트웨이로부터 잘못된 응답을 수신|

<br/>

## ❓ 주소창에 URL을 치고 엔터를 치면 흐름이 어떻게 되나요?

[링크](https://velog.io/@sylagape1231/%EC%A3%BC%EC%86%8C%EC%B0%BD%EC%97%90-naver.com%EC%9D%84-%EC%B9%98%EB%A9%B4-%EC%9D%BC%EC%96%B4%EB%82%98%EB%8A%94-%EC%9D%BC%EC%9D%84-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%B4%EB%B3%B4%EC%9E%90) 참고

<br/>
