* 웹 아키텍쳐 101 부분 중 일부를 공부하고 적은 글 입니다. (추후 업데이트 예정)

![웹아키텍처101](https://velog.velcdn.com/images/blacklabf/post/ba0221b3-286f-45cd-a8d8-f23eae780d6d/image.png)


![](https://velog.velcdn.com/images/blacklabf/post/1c61e834-b9b9-4684-81a4-a47862e894b4/image.png)

### DNS
Client가 Domain을 입력해서 들어오면 DNS가 네트워크를 타고 가서 그 Domain에 맞는 ip 주소를 찾아준다. 
(domain과 ip이 해시테이블로 저장되어있음.) 
그러면 그 ip 주소로 접속하게 된다.
### Proxy Server
#### Forward Proxy Server
* 익명성: Client랑 같은 network 망에 있는 Proxy Server에서 여러 Client들의 ip들을 하나로 묶어서 web application server에다가 전달해준다.  
#### Reverse Proxy Server
* 종류 : apache , ngnix
* 보안 : Ddos 공격등 너무 많은 요청들이 들어올 때 1차적으로 막아줄 수 있다.  
* 로드밸런싱 : 여러 요청을 웹 서버에 나눠서 포트 포워딩을 해주기 때문에 서버 과부화를 줄일 수 있다.
### CNS
* Reverse Proxy server는 동적 페이지 요청의 경우 web server에다가 포트 포워딩을 해주지만, 정적 페이청을 할 경우 CNS라는 정적 데이터 서버(이미지, 동영상, HTML)에서 가져다가 직접 처리하여 값을 반환해준다. 

![](https://velog.velcdn.com/images/blacklabf/post/62fd1435-35e1-4f6d-a185-20b1657e1b2c/image.png)

### Web Application Server
* 종류 : tomcat
* HTTP 요청이 오면 서블릿 컨테이너는 그 요청에 맞는 서블릿을 찾아서 메모리에 올려 객체를 만들고 thread를 할당한다. 
* Servlet : controller의 method, 하나의 http 요청을 처리하는 method
* Servlet Container : Servlet Thread들의 관리자 
* 처음 요청이 들어오면 Servlet 객체는 최초 1번만 생기고 요청이 들어올 때마다 thread를 만든다.
* 즉, 요청에 맞는 Servlet mapping

![](https://velog.velcdn.com/images/blacklabf/post/aa371415-29df-4bba-b608-175f63abc794/image.png)

### Spring
* servlet이 html 화면을 직접 반환하는 게 어려워서 spring이 등장했다. 
* Spring Container는 요청에 맞는 controller를 매핑 해주고 controller는 거기에 맞는 로직 처리를 하는 서비스를 매핑 해주는데 db와 관련된 로직이라면 db에 다녀온다.
* 헷갈렸던 부분 : HTTP 요청이 POST여도 READ 가능! (HTTP 요청 != CRUD)



| reference 
* https://velog.io/@onionlily123/Web-Server-VS-WAS
* https://blog.rhostem.com/posts/2018-07-22-web-architecture-101
