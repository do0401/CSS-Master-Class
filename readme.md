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

-
