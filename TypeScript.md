# TypeScript

## **타입스크립트 설치**
글로벌로 설치
```
npm install -g typescript
npm install -g ts-node
```

.ts파일을 .js파일로 컴파일
```
tsc fileName.ts
```

.ts파일을 바로 실행
```
ts-node fileName.ts
```

## **변수 선언**

### boolean, number, string
```typescript
let flag: boolean = true;

let intNum: number = 10;
let hexNum: number = 0xf; // 15

// single quote
let name: string = 'j2e4';
// double quote
let gender: string = "female";
// back quote, ${exp}
let sentence: string = `${name} is ${gender}`; // j2e4 is female
```

### array, tuple, enum
```typescript
let list: number[] = [1, 2, 3];
let genericList: Array<number> = [1, 2, 3];

let tuple: [number, string];
tuple = [1, 'number one'];

// 2차원 튜플 배열
let tupleArr: [number, string][] = [
    [1, 'number one'],
    [2, 'number two']
];

enum State {
    INIT = 0,
    READY = 1,
    PROGRESS = 2,
    DONE = 3,
    ERROR = 4
};
const errCd = State.ERROR;
console.log(State.INIT); // 0
console.log(State[errCd]) // 'ERROR'
```

tuple 타입은 ([digitalocean.com](https://www.digitalocean.com/community/tutorials/typescript-tuples))
* key-value 형태의 데이터를 다루는 데 유용하다고 한다.
* 위의 예제(1차원 배열 tuple 변수)에서 2번 index부터는 number와 string 타입 모두 대입할 수 있지만, `그 외 boolean과 같이 선언되지 않은 타입은 넣을 수 없다.`
    ```typescript
    // tuple = [1, 'number one'] 에서
    tuple.push('string'); // ok
    tuple.push(2); // ok
    tuple.push(false); // err
    ```

### any, void, 
* any: 자바스크립트처럼 변수를 `특정 타입에 종속하지 않도록 선언`하는 방법
* void: '`반환하지 않음`'을 의미

```typescript
let sure: any = 1;
sure = 'can be'; // string
sure = true; // boolean

function debug(msg, isErr): void {
    if (isErr)
        console.log('error:', msg);
	else
		console.log(msg);
}
```

