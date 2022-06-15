## 객체 개념 및 종류
- 여러 개의 프로퍼티(property)와 메소드로 구성
  - 프로퍼티 : 객체의 고유한 속성
  - 메소드(method) : 함수
- 코어 객체
  - JavaScript가 실행되는 곳 어디에나 사용 가능
  - 기본 객체로 표준 객체
  - Array, Date, String, Math 타입 등
  - 자바스크립트 코드에서 혹은 서버에서 사용 가능
- HTML DOM 객체
  - HTML 문서에 작성된 각 HTML 태그들을 객체화한 것들
  - HTML 문서의 내용과 모양을 제어하기 위한 목적
  - W3C의 표준 객체
- 브라우저 객체
  - 자바스크립트로 브라우저를 제어하기 위해 제공되는 객체
  - BOM(Brower Object Model)에 따르는 객체들
  - 비표준 객체

## 코어 객체
- 코어 객체 생성 : new 키워드를 통해 생성
  - 객체가 생성되면 객체 내부에 프로퍼티와 메소드들 존재하며, 접근은 .연산자 이용

```JavaScript
var today = new Date(); // 시간 정보를 다루는 Date 타입의 객체 생성
var msg = new String(“Hello”); // “Hello” 문자열을 담은 String 타입의 객체 생성
```
### Array 객체
- []로 배열 만들기
  - 배열 크기는 고정되지 않음, 인덱스+1로 접근해 배열 크기 늘릴 수 있음
  - 마지막 원소 추가 시 늘어남

```JavaScript
var week = ["월", "화", "수", "목", "금", "토", "일"];
var plots = [-20, -5, 0, 15, 20];
```
- Array로 배열 만들기
```JavaScript
var week = new Array("월", "화", "수", "목", "금", "토", "일");
```

- 인덱스(변수명[])를 이용해 배열의 각 원소 접근

```JavaScript
var week = ["월", "화", "수", "목", "금", "토", "일"];
var plots = [-20, -5, 0, 15, 20];
```

- length : 배열의 크기 확인

```JavaScript
var plots = [-20, -5, 0, 15, 20];
var week = new Array("월", "화", "수", "목", "금", "토", "일");
var m = plots.length; // m은 5
var n = week.length; // n은 7
```

### Date 객체
- Date : 시간 정보를 담는 객체

```JavaScript
var now = new Date(); // 현재 날짜와 시간(시, 분, 초)

var date = now.getDate(); // 오늘 날짜
var hour = now.getHours(); // 지금 시간

var startDay = new Date(2017, 2, 1); // 2017년 3월 1일 시간 객체
```

### String 객체

```JavaScript
var hello = new String("Hello");
var hello = "Hello";
var m = hello.length; // 문자열 길이 확인

var hello = new String("Hello");
var c = hello[0]; // 0번째 인덱스에 있는 문자 접근
var res = hello.concat("JavaScript"); // HelloJavaScript
```

### Math 객체
- Math : 수학 계산을 위한 프로퍼티와 메소드 제공

```JavaScript
var sq = Math.sqrt(4); // sqrt : 제곱근
var area = Math.PI*2*2; // PI : 파이

var m = Math.random()*100; // 0에서 99.999...까지 실수 난수
var n = Math.floor(m); // m에서 소수점 이하를 제거한 정수
```

### 사용자 객체
- new Object() 이용

```JavaScript
// 사용자 객체 만들기
var account = new Object(); 
account.owner = "황기태"; // 계좌 주인 프로퍼티 생성 및 초기화
account.code = "111"; // 코드 프로퍼티 생성 및 초기화
account.balance = 35000; // 잔액 프로퍼티 생성 및 초기화
account.inquiry = inquiry; // 메소드 작성
account.deposit = deposit; // 메소드 작성
account.withdraw = withdraw; // 메소드 작성
```

- 리터럴 표기법 이용

```JavaScript
//사용자 객체 만들기
var account = {
    // 프로퍼티 생성 및 초기화
    owner: "황기태",
    code: "111",
    balance: 35000,

    // 메소드 작성
    inquiry: function () {
      return this.balance;
    },
    deposit: function (money) {
      this.balance += money;
    },
    withdraw: function (money) {
        this.balance -= money;
        return money;
    }
};
```