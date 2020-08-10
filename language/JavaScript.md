# JavaScript

Array.prototype.forEach() 에서 continue
```javascript
var oddCnt = 0;
var oddSum = 0;

[1, 3, 10, 13].forEach(function (num) {
    if (num % 2 === 0)
        return;

    oddCnt++;
    oddSum += num;
});
```