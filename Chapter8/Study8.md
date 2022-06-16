## HTML DOM 객체
-  웹 페이지에 작성된 HTML 태그의 요소를 객체화 한 것

- DOM 트리
  - HTML 태그의 포함관계에 따라 DOM 객체의 트리(tree)가 생성되며, JavaScript는 DOM 트리를 통해 DOM 객체에 접근할 수 있음
  - HTML 태그 당 DOM 객체가 하나씩 생성
  - DOM 트리 루트는 document 객체

- 브라우저가 HTML 태그를 화면에 그리는 과정
1. 브라우저가 DOM 트리의 틀(document 객체) 생성
2. 브라우저가 HTML 태그를 읽고 DOM 트리에 DOM 객체 생성
3. 브라우저는 DOM 객체를 화면에 출력
4. HTML 문서 로딩이 완료되면 DOM 트리 완성
5. DOM 객체 변경 시, 브라우저는 해당 HTML 태그의 출력 모양을 바로 갱신

### HTML 태그의 요소(element)
- 엘리먼트 이름(태그 이름)
- 속성
- CSS3 스타일
- 이벤트 리스너
- 콘텐츠(innerHTML)

### DOM 객체 구성 요소
- 프로퍼티(property) : HTML 태그의 속성(attribute)
- 메소드(method) : DOM 객체의 멤버 함수로서, HTML 태그 제어
- 컬렉션(collection) : 자식 DOM 객체들의 주소를 가지는 등 배열과 비슷한 집합적 정보
- 이벤트 리스너(event listener)
  - HTML 태그에 작성된 이벤트 리스너 반영
  - 약 70여 개의 이벤트 리스너를 가질 수 있음
- CSS3 스타일
  - HTML 태그에 설정된 CSS3 스타일 시트 정보를 반영
  - DOM 객체의 style 프로퍼티를 통해 HTML 태그의 모양 제어 가능

```HTML
// DOM 객체 구성
<p id="firstP" 
style="color:blue; background:yellow"
onclick="this.style.color='teal'">
    이것은 <span style="color:red">문장입니다.
    </span>
</p>
// DOM 객체 다루기
<script>
    var p = document.getElementById("firstP"); // id가 같은 객체 찾기
    var text = "p.id = " + p.id + "\n";
    text += "p.tagName = " + p.tagName + "\n";
    text += "p.innerHTML = " + p.innerHTML + "\n";
    text += "p.style.color = " + p.style.color + "\n";
    text += "p.onclick = " + p.onclick + "\n";
    text += "p.childElementCount = " + p.childElementCount + "\n";
    text += "너비 = " + p.offsetWidth + "\n";
    text += "높이 = " + p.offsetHeight + "\n";
    alert(text);
</script>
```

### HTML DOM 객체 다루기
- innerHTML 프로퍼티 : 시작 태그와 종료 태그 사이에 들어 있는 HTML 콘텐츠
- innerHTML 프로퍼티 수정 : HTML 태그의 콘텐츠 변경

```HTML
<script>
  function change() { // change 함수
    var p = document.getElementById("firstP");
    p.innerHTML= "나의 <img src='puppy.png'> 강아지";
  }
</script>
<!-- 클릭 시 innerHTML 내용이("여기에<span style="color:red">클릭하세요</span>") change() 내용처럼 변경 -->
<p id="firstP" style="color:blue" onclick="change()">
여기에<span style="color:red">클릭하세요</span>
</p>
```

- this : 객체 자신

```HTML
<!-- <div> 태그 자신의 배경을 orange 색으로 변경 -->
<div onclick="this.style.backgroundColor='orange'">
```

- document 객체 : HTML 문서 전체
  - HTML 문서 전체를 대변하는 객체로 DOM 객체 접근 경로의 시작점, DOM 트리의 최상위 객체
  - DOM 트리에서 DOM 객체 찾기
    - document.getElementsByTagName() : 태그 이름으로 찾기
    - document.getElementsByClassName() : class 속성으로 찾기
```JavaScript
var divTags = document.getElementsByTagName("div");
```
```JavaScript
var plainClasses = document.getElementsByClassName("plain");
var n = plainClasses.length;
```
  - document.open() : 현재 브라우저에 출력된 HTML 콘텐츠를 지우고 새로운 HTML 페이지 시작
  - document.close() : 현재 브라우저에 출력된 HTML 페이지 완성으로 더 이상 document.write() 할 수 없음
  - document.createElement() : DOM 객체 동적 생성
  - parent.appendChild(DOM객체); parent.insertBefore(DOM객체 [, child]); : DOM 트리에 삽입
  - var removedObj = parent.removeChild(); : DOM 객체의 삭제

```JavaScript
// <div> 태그의 DOM 객체 동적 생성
var newDIV = document.createElement("div");
newDIV.innerHTML = "새로 생성된 DIV입니다."; 
newDIV.setAttribute("id", "myDiv");
newDIV.style.backgroundColor = "yellow"
```

```HTML
<!-- 위 자바 스크립트로 생성된 DOM 객체 정보-->
<div id="myDiv"
style="background-color:yellow">
새로 생성된 DIV입니다.
</div>
```