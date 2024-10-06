# Closures
클로저는 내부함수가 외부함수의 맥락에 접근할 수 있응 것을 말한다                
자바 스크립트는 함수 안에 또 다른 함수를 선언 할 수 있는데 내부함수는 외부함수의 지역변수에 접근할 수 있다            
```js
function outer(){
  let x = 10;
  function inner(){
    console.log(x)
  }
  return inner;
}
outer();
```
결과를 보면 10이 출력된다
