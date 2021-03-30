#### 👀 Building a website with node.js and express
---
- 회사에서 웹사이트를 제작하여 솔루션을 시연하고자 한다.
- 덕분에 하던 ~~AI 학습을 뒤로하고 급하게~~ 웹사이트를 제작해야 했다 😢
- Bootstrap의무료 template을 활용하여 제작한다.
- 처음에는 Django로 개발하였으나, node.js+Express로 변경하게 되었다.
- 사용한 소스코드 및 템플릿을 차차 업데이트하겠다.

---

##### `1. npm 설치`

- docker는 배포를 위해 사용할 것임
- 개발 툴은 pycharm으로 새로운 프로젝트/가상환경을 연결.
- 난 vsc 설치하면서 Node.js를 이미 설치하였기 때문에 이 부분은 패스
- 파이참 터미널에서 npm install [패키지명]으로 패키지를 설치할 수 있다.
- 우린 express 모듈을 설치해야 함

##### `2. express 설치`

``` bash
npm install --save express 
npm install --save ejs 
```

##### `3. index.ejs`

- 아래 내용 붙여넣고, 실행하면 localhost:3000으로 웹페이지가 열린다.

``` javascript
var express = require('express'); // 설치한 express module을 불러와서 변수에 담기!!
var app = express(); //express를 실행, app object 초기화!!

app.get('/', function(req, res) { // '/' 위치에 'get'요청을 받는 경우,
  res.send('<h1> Hello World </h1>'); // 메세지를 보내는 것입니다!!
});

var port = 3000; // 포트 번호!!
app.listen(port, function(){ 
  console.log('주소!!-> http://localhost:'+port); 
});
```

``` bash
npm start
```



##### `4. bootstrap`

- bootstrap의 template을 사용하기 위해서 설치해주어야 한다.

```bash
npm install bootstrap
```

- 모든 패키지 설치는 npm install [패키지명]으로 해주면 된다 !
