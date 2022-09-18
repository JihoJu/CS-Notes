![http1.png](../img/network/http1.png)

Image Source: https://www.suntech.org.ng/suntech_content/uploads/2018/08/Bennefits-of-SSL.png

# HTTP 란?

![http2.png](../img/network/http2.png)

Image Source: https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP_Steps.png

HTTP(Hypertext Transfer Protocol)은 client-server 아키텍처에서 정보를 전달하는 표준이다. 쉽게 말해서, HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 프로토콜이다. HTTP 는 모든 데이터 교환의 기초이며, OSI model 7계층에서 동작하며 80번 포트를 사용한다.

HTTP 프로토콜은 클라이언트와 서버 사이에서 리소스(텍스트, 이미지, 비디오 등) 교환을 용이하게 해준다. 

클라이언트와 서버 사이에서의 리소스 교환은 다음 과정으로 수행된다.

```
1. HTTP 클라이언트인 웹 브라우저/모바일 앱은 HTTP 요청을 서버의 URL 주소로 보낸다.
2. 해당 주소는 DNS 확인 후 IP 로 변환된다.
3. 웹 서버에서 HTTP 데몬 프로세스가 HTTP 요청을 처리한다.
4. 처리된 요청은 클라이언트에게 응답을 제공한다.
```

# HTTP Requests and Responses

클라이언트와 서버들은 개별적인 메시지 교환에 의해 통신한다. 보통 브라우저인 클라이언트에 의해 전송되는 메시지를 **요청(request)** 이라고 부르며, 그에 대해 서버에서 응답으로 전송되는 메시지를 **응답(response)** 라고 부른다.

## HTTP requests

HTTP requests 는 클라이언트에 의해 전송되는 것으로 필요 정보와 함께 서버에게 보내진다.

필요 정보는 다음과 같다.

- **HTTP Version**: HTTP/1.1, HTTP/2, HTTP/3
- **URL 주소**
- **HTTP Method**: 수행되어야할 특정 액션으로 GET, PUT, POST, DELETE 가 있다.
- **HTTP request headers**: 어떤 타입의 브라우저가 사용되고 있는지, 어떤 데이터를 서버로부터 받기를 원하는 지와 같은 정보를 포함한다.
- **HTTP body**: 시스템에서 사용자를 생성하기 위해 클라이언트에서 사용자의 세부 정보와 같이 전송되는 선택적 정보이다. 로그인 사용자 및 암호는 HTTP 본문으로 인코딩되어 전송된다. HTTP body 는 **페이로드(payload)** 라고 부른다.

## HTTP responses

HTTP responses 는 클라이언트의 요청(request)에 의해 서버가 클라이언트에게 보내는 데이터이다. 이 데이터는 다음 정보를 포함한다.

- **HTTP status code**: 이는 서버에서 클라이언테에게 보내진 요청에 대한 상태를 의미한다. Responses는 성공 또는 에러를 나타낼 수 있으며, 모든 오류는 400, 401, 404, 500 등과 같은 다른 오류 코드를 가진다. 성공 코드는 200 이다.
- **HTTP response headers**: 이는 서버와 요청된 리소스들에 대한 정보를 보낸다.
- **HTTP body (optional)**: 만약 요청이 성공이라면, body 는 HTML 코드 내 요청된 데이터를 포함한다. 이는 클라이언트(웹 브라우저)에 의해 웹 페이지로 변환된다. REST API의 경우, responses 에 클라이언트가 프론트엔드 단에서 데이터를 렌더링하기 위한 JSON payload를 포함한다.

# HTTPS 란?

**HTTPS (Hypertext transfer protocol secure)** 은 클라이언트와 서버 사이에 데이터 전송에 추가적인 보안을 제공하는 HTTP 버전으로 443 포트를 사용한다.

HTTPS 는 은행 계좌, 비밀번호 등과 같은 민감한 정보가 네트워크를 통해 전송할 때 이러한 데이터의 보안을 강화하기 위해 암호화 된다.

## SSL/TLS

**SSL (Secured Socket Layer)** 은 전송 데이터나 정보를 보호하기 위해 암호화를 사용한다.

**TLS (Transport Layer Security)** 는 SSL과 같은 동작으로 수행되는 향상된 SSL 버전이다.

SSL과 TLS 는 같은 의미로 사용되지만 요즘은 TLS 를 사용한다.

### HTTP + TLS = HTTPS

‘S’ 는 SSL이 연결을 보호하고 데이터를 암호화하고 있음을 의미한다.