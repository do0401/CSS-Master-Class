# CSS Master Class

이 내용은 [Nomad Coders](https://academy.nomadcoders.co/)의 니콜라스님 강의를 토대로 정리했습니다.

## `1일차`

## #1 Flexbox

### #1.1 Basics of Flexbox

- flex의 기본 개념 두 가지는 Flex-container와 Flex-item이다.
- container는 item들의 parent 이다.
- container에 flex 옵션만 주면 item들이 영향을 받는다.
- justify-content는 item들의 간격을 조절할 수 있다.
- justify-content의 default는 flex-start이다.
- flex-end는 끝쪽을 정렬해 준다.
- space-around는 item 주변에 간격을 만들어 준다.

### #1.2 Main Axis and Cross Axis

- flex는 item들의 정렬 기준이 row냐 column이냐에 따라 메인 축이 정해진다.
- flex의 기본 정렬 기준은 row이다.
- #1.1에서 알아본 justify-content는 메인 축에 영향을 미친다.
- 반대로 크로스 축은 align-items가 영향을 주는 축이다.
- flexbox direction이 row이면, main 축은 수평 / cross 축은 수직,
- flexbox direction이 column이면, main 축은 수직 / cross 축은 수평

### #1.3 Flex Wrap and Direction

- flex 의 기본 옵션은 no-wrap이다.
- no-wrap 은 item들을 최대한 압축해서 한 줄에 들어오도록 한다.
  `flex-wrap: wrap;`
- 하지만 wrap 옵션을 적용하면 item을 줄바꿈한다.
- wrap 속성을 사용할 때 `justify-items: center;` 옵션을 함께 사용하면 더 깔끔하다.
- flex-direction 은 item 정렬 방식을 바꿔줄 수 있다.
- flex-direction 기본 옵션은 row 이다.

### #1.4 Align Self and Flexbox Conclusions

- align-self는 container가 아닌 item에 직접 옵션을 주는 속성이다.
- align-self는 cross axis에서 각각의 아이템에 대해 정렬을 하는 것이다.

## `2일차`

## #2 CSS Grid

### #2.1 Basic CSS Grid

- grid 속성을 사용하려면 flex와 마찬가지로 container에 `display: grid;`를 준다.
- 또한 grid 에도 rows, columns 개념이 있다.
- `grid-template-columns: 30px;` 이라고 주면 grid는 하나의 컬럼만을 가지게 된다.
- `grid-template-rows: 30px;` 를 추가로 주면 가로 세로 30px을 가지는 박스를 하나 얻을 수 있다.
- 여러 개의 column과 row를 가지고 싶다면 아래와 같이 추가해 주면 된다.

```css
grid-template-columns: 30px 50px;
grid-template-rows: 30px 12px;
```

- 이것이 css grid에서 레이아웃을 짜는 방법이다.
- `grid-gap: 10px;` 을 주면 각 column과 row 사이에 여백을 준다.

### #2.2 Auto Rows and Columns

- 만약 매우 많은 element 들이 있는데 위 #2.1에서처럼만 선언한다면 단 4개의 element만 보여질 것이다.
- grid는 2개의 row, 2개의 column만 놓으면 된다고 이해하고 있기 때문이다.
- 이러한 문제를 해결하려면 auto-rows / auto-columns 를 사용하면 된다.
- api 콜을 해서 얼마나 많은 수의 row와 column이 필요할지 모를 때 auto 로 정의해놓을 수 있다.
- `grid-auto-rows: 60px;` 이라고 정의하면 위에서 `grid-template`으로 정의해놓은 element를 제외하고 정의되지 않은 element들의 row가 60px로 자동 설정된다.
- 이번엔 `grid-auto-columns: 60px;` 을 정의하면 작동하지 않는다.
- 그 이유는 grid도 flex와 비슷한 성질을 가지고 있기 때문이다.(flex-direction과 비슷한 속성 존재)
- 초과로 존재하는 children이 있을 때 row / column 어디에 놓을지 결정하는 속성이 있다.
- `grid-auto-flow` 라는 속성이며 기본적으로 row 이다.
- 이 속성을 column으로 바꾸고 다시 `grid-auto-columns`를 주면 이번엔 작동한다.
- 하지만 보통의 경우에는 `grid-auto-rows` 기본 속성만 사용할 것이다.
- 웹에서 대부분 위에서 아래로 보여지기 때문이다.

### #2.3 Grid Template Areas

```css
.container {
  grid-template-areas:
    "header header header"
    "content content sidebar"
    "content content sidebar"
    "footer footer footer";
}
.first {
  grid-area: header;
  background-color: #f1c40f;
}
.second {
  grid-area: sidebar;
  background-color: #27ae60;
}
.third {
  grid-area: footer;
  background-color: #3498db;
}
.forth {
  grid-area: content;
  background-color: #d35400;
}
```

- 위와 같이 정의를 하면 `grid-template-areas` 에서 선언한 위치에 각각의 `grid-area`가 배치된다.
- 화면에 공간들을 그리고 안을 채우는 것과 같다.
- element들의 사이즈를 주고 싶다면 `grid-auto-rows` 로 높이를 줄 수 있다.
