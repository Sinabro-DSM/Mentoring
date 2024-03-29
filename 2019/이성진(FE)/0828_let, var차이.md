# javascript의 변수 선언

### 1. var
- var은 javascript 초기에 나온 변수 선언 방식이다.

### 2. var의 단점
- var로 선언된 변수는 많은 문제가 있었다. 
그 중에서도 변수의 범위가 문제였다.
일반적으로 스코프 안에 선언된 변수는 그 스코프 안에서만 범위가 유효하다.
하지만 ES5이하 버전에서는 범위가 함수로만 적용이 되었다.
- 따라서, 제어문같은 블록 범위의 변수는 var가 스코프 밖에서도 유효하다는 엄청난 문제가 있다.
``` javascript
if(true) {
    var a = 1;
}
console.log(a);
> 1
```

### 3. let
- 이런 var의 문제를 해결하기 위해 ES6부터는 let이라는 변수 선언 방식이 탄생했다.

### 4. let의 장점
- let은 함수와 블록 스코프 모두에 범위가 유효하다.
- 앞서 보여주었던 코드를 let을 이용하여 작성하면 오류가 난다.
``` javascript
if(true) {
    let a = 1;
}
console.log(a); // Uncaught ReferenceError: a is not defined
```
### 5. const
- const는 다른 언어에서도 자주 사용하는 변수 선언 방식이다.
- const는 상수로서, lvalue가 될 수 없다.
``` javascript
const a = 1;
a = 2; // Uncaught TypeError: Assignment to constant variable.
```

## 궁금한 점
예전에 var과 let의 빠르기에 관한 이야기를 접한 적이 있습니다.
정확하게 기억하지는 못 하지만, 브라우저가 var과 let을 만날 때 빠르기에 차이가 있나요?
만약 있다면 브라우저가 var과 let중 더 좋아하는(?), 더 빠르게 진행하는 선언 방식은 무엇인가요?

## 답변
불과 몇 년 전 var과 let의 성능차이는 압도적으로 var가 성능이 좋았습니다.
하지만 브라우저들이 수시로 최적화를 하면서 차이를 줄였습니다.
현재는 var과 let의 성능차이를 가르는 것은 <strong>브라우저, 상황</strong>입니다.
그럼에도 불구하고 let을 사용하는 이유는 앞서 말했듯이 스코프 유효범위를 인정하기 때문입니다.

## 회고 
var과 let을 혼용해서 쓴 나를 반성하는 계기가 되었다.
앞으로는 let을 사용하겠다.

# 멘토 코멘트 
## 칭찬할 점
질문이 좋았다. 깊게 공부하려고 하는 것 같아서 좋다.

## 노력할 점 
없음~~

## 다음 계획 
자바스크립트 개념 다지기

## 그 외