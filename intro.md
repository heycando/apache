## WAS, web server, web service
### apache/ nginx
### wsgi 

* 클라이언트에서 서버에 HTTP 요청을 보내면 웹서버가 해당 내용이 정적파일에 대한 요청인지 확인후, 맞으면 그대로 응답합니다. 아니라면 WAS에 요청을 넘깁니다. WAS는 해당 요청을 App이 알 수 있는 형태로 넘기고 App에서 실질적인 데이터를 처리하여 응답
  * https://chrisjune-13837.medium.com/web-%EC%9B%B9%EC%84%9C%EB%B2%84-%EC%95%B1%EC%84%9C%EB%B2%84-was-app%EC%9D%B4%EB%9E%80-692909a0d363
* wsgi? https://sgc109.github.io/2020/08/15/python-wsgi/
* ????
* https://velog.io/@misun9283/WSGI-%EB%9E%80
* https://www.youtube.com/watch?v=NyhbNtOq0Bc
* 미들웨어, was, web
  * https://velog.io/@mzsw/%EC%9B%B9%EC%84%9C%EB%B2%84-WAS-%EB%9E%80
* rpc -> 분산 데이터 처리.. (client<-> server model에서 나아가서), 서버 기능 최소화
  * https://www.youtube.com/watch?v=oawaAfkKo7k
* gRPC  
  * https://medium.com/naver-cloud-platform/nbp-%EA%B8%B0%EC%88%A0-%EA%B2%BD%ED%97%98-%EC%8B%9C%EB%8C%80%EC%9D%98-%ED%9D%90%EB%A6%84-grpc-%EA%B9%8A%EA%B2%8C-%ED%8C%8C%EA%B3%A0%EB%93%A4%EA%B8%B0-1-39e97cb3460
