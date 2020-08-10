# CSS

### flex
container의 elements를 원하는 방향, 원하는 크기로 정렬할 수 있게 해준다.
```html
<div class="container">
    <div class="element">a</div>
    <div class="element">b</div>
    <div class="element">c</div>
</div>
```
```css
.container {
    display: inline-flex;
    flex-direction: column;
}
/*
    a
    b
    c
*/
```

container에 적용: 
 * display: flex, inline-flex
 * flex-flow (flex-direction, flex-wrap)
 * justify-content
 * align-content
 * align-items

element에 적용:
 * flex (flex-grow, flex-shrink, flex-basis)

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

### flex 속성 (flex-grow flex-shrink flex-basis의 shorthand)
```css
flex: 0 1 auto;
/*
    same with flex: initial;
    엘리먼트의 너비/높이에 따라 크기가 정해진다.
    컨테이너의 크기를 넘기지 않기 위해 줄어들 순 있으나(flex-shrink: 1), 공간을 채우진 않는다(flex-grow: 0).
*/
```
```css
flex: 1 1 auto;
/*
    same with flex: auto;
    엘리먼트의 너비/높이에 따라 크기가 정해진다.
    컨테이너의 크기를 넘기지 않기 위해 줄어들 수 있고(flex-shrink: 1) 공간을 채우기 위해 늘어날 수 있다(flex-grow: 1).
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
