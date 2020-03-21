# 3장. Node.js 이해

- 비동기 프로그래밍 : I/O 처리 요청만 운영체제에 전달하고 CPU는 다른 연산을 수행한다. I/O 처리가 완료되면 운영체제에서 처리 완료 메시지를 전달 받아 이후 작업을 처리하는 방식이다.

  ~~~javascript
  function func(cb) {
      cb('callback');
  }
  
  func((param) => {
      console.log(param);
  });
  ~~~

  위 함수는 비동기 프로그래밍처럼 보이지만 동일한 스레드 위에서 동기적으로 동작한다.

  함수 내부에서 **비동기적으로 콜백**하기 위해서는 **process.nextTick** 함수를 이용해야 한다.

  ~~~javascript
  function func(cb) {
      process.nextTick(cb, 'callback');
  }
  
  try {
      func((param) => {
          a.a = 0; // 에러 발생 a is not defined
      });
  } catch(err) {
      console.log('exception');
  }
  ~~~

  위 코드는 a.a = 0 부분에서 에러가 발생하여 exception이 나와야 하지만 process.nextTick으로 인해서 try catch문과 콜백함수가 다른 스레드 위에서 동작하여 catch에 잡히지 않는다.

- Node.js는 싱글 스레드 기반으로 동작하지만 모두 같은 스레드 위에서 동작하지는 않는다. 따라서 try catch문 만으로 모든 예외 처리를 하기에는 무리가 있다.

- uncaughtExeption : 위와 같은 문제를 해결하기 위해서 모든 스레드에서 예외 처리를 할 수 있는 이벤트.

  ~~~javascript
  function func(cb) {
      process.nextTick(cb, 'callback');
  }
  
  try {
      func((param) => {
          a.a = 0;
      });
  } catch (err) {
      console.log('exception');
  }
  
  process.on('uncaughtException', (error) => {
      console.log('uncaughtException');
  });
  ~~~

  위 코드처럼 try catch만으로 제어할 수 없던 예외를 uncaughtException 이벤트로 제어할 수 있다.



- Node.js로 http 서버 만들기

  ~~~javascript
  const http = require('http'); // Node.js의 기본 모듈
  
  const server = http.createServer((req, res) => { // http 서버 인스턴스 생성
      // 서버 로직
  }).listen(8000); // 서버에 포트 할당
  ~~~

- Node.js로 http 클라이언트 만들기

  ~~~javascript
  const http = require('http'); // Node.js의 기본 모듈
  
  const options = { // 요청할 서버의 정보, 페이지 정보
      host: '127.0.0.1',
      port: 8000,
      path: '/'
  };
  
  const req = http.request(options, (res) => {
      let data = '';
      res.on('data', (chuck) => { // 데이터 수신 이벤트
          data += chunk;
      });
      
      res.on('end', () => { // 수신 완료 이벤트
          console.log(data);
      });
  });
  
  req.end(); 
  ~~~

- TCP 서버 만들기

  ~~~javascript
  const net = require('net'); // Node.js의 기본 모듈
  
  const server = net.createServer((socket) => { // TCP 서버 생성
      socket.end('hello world'); // 접속시 응답
  });
  
  server.on('error', (err) => { // 에러 처리
      console.log(err);
  });
  
  server.listen(9000, () => { // 9000 포트 리슨
      console.log('listen', server.address());
  });
  ~~~

- TCP 클라이언트 만들기

  ~~~javascript
  const net = require('net'); // Node.js의 기본 모듈
  
  const options = { // 접속할 서버 정보
      port: 9000,
      host: '127.0.0.1'
  };
  
  const client = net.connect(options, () => { // 서버 접속
      console.log('connected');
  });
  
  client.on('data', (data) => { // 데이터 수신
      console.log(data.toString());
  });
  
  client.on('end', () => { // 서버 접속 종료
      console.log('disconnected');
  });
  ~~~

  