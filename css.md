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

### flex-flow 속성 (flex-direction flex-wrap의 shorthand)
```css
flex-flow: column wrap;
/*
    flex-direction flex-wrap 순서
    
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

### 중앙 정렬하기
```css
display: flex;
align-items: center;
/* 또는 */
display: inline-flex;
align-items: center;
```

### 가운데 정렬하기

지금까지는 보통 `text-align: center;` 했는데  
`display: flex;` 스타일을 많이 쓰게 되면서 `text-align`으로 가운데 정렬 스타일이 적용이 안 되길래 찾아봤다.

```css
display: flex;
justify-content: center;
/* 또는 */
display: inline-flex;
justify-content: center;
```

