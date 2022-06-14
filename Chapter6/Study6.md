## JavaScript
-  웹 프로그래밍 개념 창시
-  HTML 문서에 내장되어 조각 소스 코드라고도 함
-  스크립트 언어
   -  인터프리터 실행
   -  컴파일 필요 없음
-  C언어 구조를 차용해 배우기 쉬움
-  마우스와 키보드 입력은 오직 자바스크립트로만 가능하며 계산 기능이 있음
- 웹 페이지 내용 및 모양의 동적 제어가 가능
- 브라우저 제어 기능
  - 브라우저 윈도우 크기와 모양 제어
  - 새 윈도우 열기/닫기
  - 다른 웹 사이트 접속
  - 히스토리 제어
- 웹 서버와의 통신 기능
- 웹 애플리케이션 작성 기능

### JavaScript 코드 위치

1. HTML 태그의 이벤트 리스너 속성에 작성
```JavaScript
onmouseover = "this.src='media/banana.png'" //마우스를 올릴 경우
onmouseout = "this.src='media/apple.png'" // 마우스가 이미지에서 나올 경우
```
2. <script></script> 태그에 작성

```JavaScript
<script>
    function over(obj) {
        obj.src = "media/banana.png";
    }

    function out(obj) {
        obj.src = "media/apple.png";
    }
</script>

<img src="media/apple.png" alt="이미지" onmouseover="over(this)" onmouseout="out(this)">
</body>

```
1. JavaScript 파일에 작성
```HTML
<script src=“파일이름.js”> // HTML5부터 이곳에 자바스크립트 코드 추가 작성하면 안 됨
</script>

```
1. URL 부분에 작성
```HTML
<a href="javascript:alert('클릭하셨어요?')">
```

### JavaScript 출력
- document.writeln(), document.write() : 웹 페이지에 출력

```JavaScript
document.write("<h3>Welcome!</h3>");
```

- Dialog(대화상자) : 
  - 스타일링이 안된 상태로 스크립트가 일시 정지
  - 빠르고 간단하다는 장점이 있음
  - alert : 알림 대화상자
  - prompt : 입력 대화상자
  - confirm : 확인 대화상자

```JavaScript
let name = prompt("이름을 입력: "); // 입력 대화상자
alert("환영 " + name + "님"); // 환영 (name)님
alert(`환영 + ${name} + 님`); // 환영 + (name) + 님
let isGood = confirm("Are you Good?"); // 확인 대화상자
console.log(isGood);
```

### JavaScript 식별자 규칙
- 첫 번째 문자에는 알파벳(A-Z, a-z), 언더스코어(_), $ 문자만 사용 가능
- 두 번째 문자부터는 알파벳, 언더스코어(_), 0-9, $ 사용 가능
- 대소문자는 구분되어 다루어짐
- 자바스크립트 예약어 사용 불가

### JavaScript 문장 규칙
- 문장과 문장을 구분하기 위해 세미콜론(;) 사용

### JavaScript 데이터 타입과 리터럴
- number : 정수 또는 실수
  - 정수 : let n = 015, 15, 0x15
  - 실수 : let n = 0.1234, 0.1234E-4
- boolean : true 또는 false
  - 논리 : true, false

```JavaScript
let a = true;
let b = false; // 숫자 0, 빈 문자열, null, undefined으로도 가능
let name = "kdh";
let age = 22;
console.log(age > 30); // false
console.log(name = `kdh`);
```

- string : 문자열, 문자 타입은 없음
  - 문자열 : "" 또는 ''
- object : 객체

- 기타
  - null : 값이 없으며 Null과 NULL과는 다름
  - NaN : 수가 아님
  - undefined : 값이 할당되지 않은 상태

```JavaScript
let age;
console.log(age); //undefined
let user = null;  //user는 존재하지 않는다.
```

- typeof : 타입 확인을 하며, 다른 개발자가 선언한 변수 타입 체크 필요함
```JavaScript
let name = "kdh";
console.log(typeof 3); // number
console.log(typeof name); // string
console.log(typeof true); // boolean
console.log(typeof "123"); // string
console.log(typeof null); //object, null은 객체가 아닌 자바스크립트 오류
console.log(typeof undefined); //undefined
```

### 변수
- var : 자바스크립트 언어가 도입될 때부터 있었고 지금도 사용
- let : var을 사용할 때 변수 재 선언을 줄이기 위함
  - 동일한 변수 재 선언 시 기존 변수가 제거됨
- const : 변하지 않는 값을 선언

```JavaScript
// var 키워드로 변수 선언
var score;
var year, month, day;
var address = "서울시"; // 서울시로 초기화

// let 키워드로 변수 선언
let name = "KDH";
let name = "JAVA";

// var나 let 없이 선언
age = 21; // age가 이미 존재할 경우 기존 age에 저장

// 상수 선언
const BIRTHDAY 
```

```JavaScript
let name = "kdh";
alert(`hello ${1+2}`); // hello 3
alert(`hello ${"name"}`); // hello name
alert(`hello ${name}`); // hello kdh
```

- 전역 변수
  - 함수 밖에서 선언하거나 var/let 키워드 없이 선언
- 지역 변수
  - 함수 내에서 let으로 선언
- 블록 변수
  - if, while, for 등의 블록 내 선언

```JavaScript
let x; // 전역 변수 x 선언
function f() {
    let y; // 지역 변수 y 선언
    x = 10;
    y = 20;
    z = 30; // 전역 변수 z 선언
    if (y == 20) {
        let b = 40; // 블록 변수 b 선언
        b++;
    }
    // 변수 x, y, z 접근 가능
}
// 변수 x와 z만 접근 가능
```

- this : 지역 변수와 전역 변수 이름이 같을 경우 this로 전역 변수에 접근, let로 선언된 전역 변수는 접근 불가능

```JavaScript
var x; // 전역변수
function f() {
    var x; // 지역변수
    x = 1; // 지역변수 x
    this.x = 100; // 전역변수 x
}
```

- 연산

```JavaScript
const i = 1 / 0
const name = "kdh";
console.log(i); // Infinity
console.log(name / 2); // Nan
```

```JavaScript
let name = `kdh`;
let a = `나는 `;
let b = ` 입니다`;
console.log(a + name + b); // 나는 kdh 입니다
let age = 22;
console.log(a + age + `살` + b); // 나는 22살 입니다
```

### 함수
- 함수
  - 목적을 가지고 작성된 코드 블록
  - 데이터 전달받아 처리한 후 결과를 돌려주는 코드 블록

```JavaScript
function adder(a, b) {
    let sum;
    sum = a + b;
    return sum;
}
```

```JavaScript
<head>
    <script>
        function adder(a, b) { // 함수 작성
            let sum;
            sum = a + b;
            return sum;
        }
    </script>
</head>

<body>
    <h3>함수 adder()</h3>
    <hr>
    <script>
        let n = adder(24567, 98374); // 함수 호출
        document.write("24567 + 98374는 " + n + "<br>");
    </script>
</body>
```

- 전역 함수
  - eval(exp) : exp의 JavaScript 식을 계산
  - parseInt(str) : str 문자열을 10진 정수로 변환
  - parseInt(str, radix) : str 문자열의 radix 진수로 해석 후 10진 정수로 변환
  - isFinite(value) : value가 숫자면 true
  - isNaN(value) : value가 숫자가 아니면 true

- use strict : 엄격 모드 적용

```JavaScript
"use strict"; // 엄격 모드 활성화
age = 22; //Uncaught ReferenceError: age is not defined
```