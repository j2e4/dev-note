# CSS

### flex-direction 속성
* global values: [inherit|initial|unset]
```css
flex-direction: row; // 옆으로 나열
flex-direction: row-reverse; // 역순서로 옆으로 나열
flex-direction: column; // 아래로 나열
flex-direction: column-reverse; // 역순으로 아래로 나열
```

### flex-wrap 속성
* global values: [inherit|initial|unset]
```css
flex-wrap: wrap; // 복수 행에 나열
flex-wrap: wrap-reverse; // 복수 행에 역순으로 나열
flex-wrap: nowrap; // 한 행에 나열(영역을 벗어나게 될 수 있다)
```

### flex-flow 속성 (flex-direction flex-wrap의 shorthand)<br>
```css
flex-flow: column wrap;
/*
    1 2
    3 4
    5 6
*/
```

### 영역 밖의 글자 생략하기 (...)
```css
/* 자꾸 까먹어서 적어놓는다 */
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
```