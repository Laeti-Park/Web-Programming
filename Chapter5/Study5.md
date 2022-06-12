## 배치
- CSS3으로 HTML 태그가 출력되는 위치를 원하는 곳에 지정

### 블록 박스와 인라인 박스
- HTML 태그는 인라인 태그와 블록 태그로 분류하며, 인라인 태그는 인라인 박스, 블록 태그는 블록 박스로 출력

```HTML
<!--블록 박스-->
<div>DIV</div>
<div>DIV</div>
<div>DIV</div>
```
![](../Img/study5_1.png)

```HTML
<!--인라인 박스-->
<div>DIV 내 <span>span</span>과<span>span</span>입니다</div>
<div>DIV 내 <span>span</span>과<span>span</span>입니다</div>
<div>DIV 내 <span>span</span>과<span>span</span>입니다</div>
```
![](../Img/study5_2.png)

### display
- display : 태그를 박스로 지정
- block(블록 박스)
  - 항상 새 라인에서 시작
  - 블록 박스 내에만 배치
  - 옆에 다른 요소 배치 불가능
  - width와 height으로 크기 조절 가능
  - padding, border, margin 조절 가능
```CSS
span { 
    display : block;
}
```

- inline
  - 기존 라인 안에 존재
  - 보든 박스 내 배치 가능
  - 옆에 다른 요소를 배치할 수 있음
  - width와 height으로 크기 조절 불가능
  - margin-top, margin-bottom 조절 불가능
```CSS
div div {
    display : inline;
}
```
- inline-block
  - inline
    - 기존 라인 안에 존재
    - 보든 박스 내 배치 가능
    - 옆에 다른 요소를 배치할 수 있음
  - block
    - width와 height으로 크기 조절 가능
    - padding, border, margin 조절 가능
```CSS
div div {
    display : inline-block;
}
```
![](../Img/study5_3.png)

### position
- 웹 페이지에 나타난 순서대로 HTML 태그 배치하는 방식인 normal flow를 position을 이용해 무시할 수 있음
- static
  - 정적 배치(디폴트값)
- relative
  - 상대 배치, 상대 배치에 따라 위치 지정
- absolute
  - 절대 배치, 절대적인 위치 지정
- fixed
  - 고정 배치, 브라우저 크기까지 고려해 위치 지정
- float
  - 유동 배치, 브라우저 크기까지 고려해 위치 지정
  - float : left, float : right가 있음
- position 프로퍼티를 사용할 경우, 태그의 위치와 크기
  - top, bottom, left, right, width, height  

![](../Img/study5_4.png)

### CSS3 꾸미기

- z-index : z축 우선 순위 지정

```CSS
#spadeA { z-index : -3; left : 10px; top : 20px; }
#spade2 { z-index : 2; left : 40px; top : 30px; }
```

![](../Img/study5_5.png)

- visibility : 공개 여부 지정, 적용된 텍스트는 공간을 차지하나 공개 여부에 따라 보여지거나 보여지지 않을 수 있음

```CSS
span { 
    visibility : hidden;
}
```

- overflow
  - hidden : 박스를 넘어가면 내용 숨기기
  - visible : 박스를 넘어가서도 내용 출력
  - scroll : 박스에 스크롤바 생성


- list-style-type : 아이템 마커 타입 지정
  - none, disc(●), circle(○), square(■), decimal(1)
- list-style-image : 아이템 마커 이미지 지정
  - list-style-image : url("이미지 주소");
- list-sytle-position : 아이템 마커 출력

```CSS
ul { 
    background : goldenrod;
    padding : 10px 10px 10px 50px;
    list-style-position : inside;
}
```
![](../Img/study5_6.png)

- list-style : 위 3개 모두 지정


