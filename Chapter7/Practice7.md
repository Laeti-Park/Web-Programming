### 1. 자바스크립트 객체를 생성할 때 사용하는 키워드는?
1. creat
2. +
3. new 
4. make

> 답 : 3

### 2. 다음 중 값 1,2,3으로 초기화한 배열 values를 생성하는 자바스크립트 코드는?
1. let values [] = {1, 2, 3}; 
2. let values = {1, 2. 3};
3. let values [] = [1, 2, 3]; 
4. let values = [1, 2, 3]; 

> 답 : 4

### 3. 다음 배열에 대한 설명 중 틀린 것은?

```JavaScript
let month = new Array("Jan", "Feb", "March");
```

1. let months = ["Jan", "Feb", "March"]; 로 대신할 수 있다.
2. months. length는 3이다.
3. months [1] = "February"; 코드는 "Feb"을 "February"로 수정한다.
4. months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.

> 답 : 4  
> length는 배열 크기를 확인  
> 인덱스+1을 통해 배열 크기를 늘릴 수 있음  

### 4. 다음 배열에 대한 설명 중 틀린 것은? 

```JavaScript
let grades = new Array("A", "B", "C", "D"); 
```

1. grades[4] = "F";를 실행하면 grades 배열의 크기가 1 늘어난다.
2. grades[3] = 70;은 잘못된 코드이다. 왜냐하면 문자열 배열에 정수를 넣기 때문이다.
3. grades.reverse()를 호출한 결과 grades 배열 내부가 ["D", "C", "B", "A"]로 변한다.
4. grades.length는 4이다.

> 답 : 2

### 5. 주석에 맞게 다음 빈 칸에 자바스크립트 코드로 채워라.

> 답 :  
> money = new Array(2)  
> money[0]  
> money[1]  
> money[2]  
> money.length  
> sum/money.length  

```JavaScript
let money = new Array(2) // Array를 이용하여 크기가 3인 배열 money 생성
money[0] = 5; // money의 첫 번째 원소에 5 삽입
money[1] = 5; // money의 두 번째 원소에 7 삽입
money[2] = -3; // money의 세 번째 원소에 -3 삽입
let sum = 0;
for (let i = 0; i < money.length; i++) sum += money[i]; // 배열 합 구하기
document.write(sum/money.length); // 평균 출력
```

### 6. 코어 객체에 대한 설명으로 잘못된 것은?
1. let d = new Date();로 생성한 객체 d는 현재 시간 값을 가진다.
2. Math 객체는 new Math() 로 생성하지 않고 사용할 수 있다.
3. "text"는 String 객체이다.
4. new Array()로 생성한 객체는 []로 생성한 배열과 약간 다르다.

> 답 : 4  

### 7. 다음 자바스크립트 코드가 있을 때, 아래 각 항목의 실행 결과 변수 x의 값은 무엇인가?

```JavaScript
let text = "Web Programming"; 
```

- let x = text.length;
> 답 : 15

- let x = text[2];
> 답 : "b"

- let x = text.split(" ").length;
> 답 : 2

- let x = text.replace("Web", "HTML5");
> 답 : HTML5 Programming

- let x = text.charAt(4); 
> 답 : "P"

### 8. 1부터 10 사이(10 프함) 임의의 정수를 리턴하는 자바스크립트 코드를 let x = Math.random()*10+1;로 작성하면 안 되는 이유를 설명하고, 바르게 수정하라.

> 이유 : 실수 값으로 리턴되기 때문에 floor를 사용함
> 답 : x = Math.floor(x);

### 9. student 객체를 생성하는 다음 코드를 리터럴 표기 방식으로 다시 작성하라.

```JavaScript
let student = new Object();
student.id = 1;
student.name = "kitae";
student.grade = 3.9;
```

```JavaScript
let student = {
    id : 1,
    name : "kitae",
    grade : 3.9
};
```

### 10. 리터럴 표기 방식으로 작성된 다음 box 객체가 있다.

```JavaScript
let box = {
    color : "red",
    size : 10,
    amount : 0,
    fill function() { this.amount += 2; }
    consume : function() { this.amount -= 2; }
};
```

- box 객체를 new Object()를 이용하는 방법으로 다시 작성하라. 

```JavaScript
답 : 
function fill() {
    return this.amount += 2;
}
function consume() {
    return this.amount -= 2;
}

let box = new Object();
box.color = "red";
box.size = 10;
box.amount = 0;
box.fill = fill;
box.consume = consume;
```

- 다음 주석에 지정된 대로 자바스크립트 코드를 작성하라.

```JavaScript
답 : 
box.fill(); // box 객체의 fill() 메소드 호출
document.write(box.amount); // document.write()로 amount 프로퍼티 값 출력
box.consume(); // box 객체의 consume() 메소드 호출
document.write(box.amount); // document.write()로 amount 프로퍼티 값 출력
```

- 앞의 문제의 실행 결과 출력되는 것은 무엇인가?
20