## var, const, let

변수를 선언할때 사용됨 하지만 모두 다름

### var

var는 생성과정에서 선언, 초기화, 할당이 모두 따로 발생

호이스팅이 일어나도 오류가 발생하지 않는다.

```js
console.log(x)//undefined
var x = 1;
```

현재는 사용되지 않는데 이유는 재정의가 가능해서임

### const

const로 선언된 값은 변하지않는다.

### let

const와 달리 값을 재정의할 수 있다.

## 배열

```jsx
const arr = [1,2,3];
const arr = new Array(1,2,3);
const arr = new Array(3);// 인수가 하나면 그 인수는 배열의 길이이다.
```

## 배열 메서드

### sort()

배열의 요소를 정렬한다.

```js
const arr = [1,4,3,2,5];

const sort_arr = arr.sort();아무것도 없으면 유니코드 순서대로 정렬
const sort_arr2 = arr.sort((a,b)=>b-a);

console.log(sort_arr); 5,4,3,2,1
console.log(sort_arr2); 5,4,3,2,1
```

### join()

배열을 문자열로 반환한다.

```js
const arr = ['L','E','E'];

console.log(arr.join('')); //LEE
```

### **reverse()**

배열의 순서를 반대로 뒤집는다.

```js
const arr = ['L','E','E'];

console.log(arr.reverse()); //LEE
```

### slice()

배열의 특정 부분만 반환해준다.

```js
const arr = [1,2,3,4,5];

const slice = arr.slice(3);
const slice2 = arr.slice(1,4);

console.log(slice);//[4,5];
console.log(slice2);//[2,3,4];
```

### map()

배열의 아이템을 순서대로 받아 map안에 명령문을 실행한다.

```js
const arr = [1,2,3,4,5];
const res = 0;

arr.map(item=>res+=item);

console.log(res);//15
```

### push()

배열의 끝에 새로운 아이템을 추가해준다.

```js
const arr = [1,2,3,4,5];

arr.push(6);

console.log(arr);//[1,2,3,4,5,6]
```

## 비동기

비동기는 특정코드의 로직이 끝날때까지 기다리지 않고 나머지 코드를 먼저 실행하는 것이다

하지만 동기적으로 불러와야할때가 있으면 콜백함수를 사용한다

콜백이 너무 많아지면 코드가 복잡해지고 에러처리도 어려워진다 그래서 Promise를 사용한다

Promise는 3개의 상태가 있다

- **대기(Pending):** 비동기 함수가 아직 시작하지 않은 상태
- **성공(Fulfilled):** 비동기 함수가 성공적으로 완료된 상태
- **실패(Rejected):** 비동기 함수가 실패한 상태

Promise가 대기에서 상태가 바뀌면 then(), catch() 함수를 사용해 성공상태 또는 실패상태의 Promise를 각각 처리할 수 있다

```js
paymentWidget.requestPayment({
  orderId: "t9JI0Bs1SVdJxRs8yjiQJ",            
  orderName: "토스 티셔츠 외 2건",                    
})
.then(function (data) {
  console.log(data);
	// 성공 처리
})
.catch(function (error) {
	// 에러 처리
  if (error.code == "NEED_CARD_PAYMENT_DETAIL") {
    console.log(error.message);
  }
```

then() 체인을 길게 이어나가면 콜백과 마찬가지로 코드의 가독성이 떨어진다

### **async/await**

콜백, Promise 체인의 단점은 `async`와 `await`로 보완할 수 있다
async를 함수 앞에 붙이면 이 함수는 비동기적이고 **Promise를 반환한다는 것이다**

await은 async안에서만 사용가능한데 await을 붙이면 promise의 상태가 바뀔때까지 코드가 기다린다

```js
async function test() {
  await delay(1000);
  await delay(2000);
  const result = await Promise.resolve('끝');
  console.log(result);
}
```

### 패턴

```jsx
var pattern = /a/;
var pattern = new RegExp('a');
```

### RegExp.exec()

```jsx
console.log(pattern.exec('abcdef'));
실행결과 문자열 a를 값으로 하는 배열을 리턴함
console.log(pattern.exec('bcdefg'));
a가 없어 null 반환

var pattern = /a./;
console.log(pattern.exec('abcdef'));
실행결과 ab값으로 하는 배열을 리턴함 .은 하나의 문자를 의미 
var pattern = /a/i; 대소문자 구별 x
var pattern = /a/g; 패턴에 해당하는 문자 전부
var pattern = /a/ig; 도 가
```

### RegExp.test()

```jsx
console.log(pattern.test('abcdef'));
a가 있어서 true
console.log(pattern.test('bcdefg'));
a가 없어서 false
```

### String.match()

```jsx
console.log('abcd'.match(pattern)); 배열 a 반환
console.log('bcd'.match(pattern)); null
```

### String.replace()

```jsx
console.log('abcd'.replace(pattern, 'A')) Abcd
```
