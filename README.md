# 시나브로 멘토링
## 목적 
시나브로는 동아리원의 상호 성장을 목표로 하는 동아리다. 멘토링은 동아리의 목표를 이루기 위한 활동의 일환이며, 멘토링을 받는 사람뿐만 아니라 멘토링을 하는 사람도 함께 성장하는 것이 최종 목적이다. 또한 멘토링 진행 상황을 기록하여 데이터를 축적하고, 축적된 데이터를 바탕으로 멘토링 커리큘럼을 수정한다.

## 디렉토리 구조 및 네이밍 룰
- YYYY
    - mentee's name(field)
        - MMDD_(분류)_주제.md

### 예시 
- 2019
    - 강한나(BE)
        - 0311_서버동작원리.md
        - 0318_REST.md 
        - 0325_파이썬_자료형.md

## 마크다운 형식 
``` md
# 주제를 작성하세요
배운 것을 작성하세요.

## 궁금한 점
궁금한 점을 한 개 이상 작성하세요.
스스로 해결했다면 해결 방법과 참고한 문서 링크를 함께 첨부하고,
멘토에게 질문했다면 멘토의 답변을 자신이 이해한 대로 작성하세요.

## 회고 
이번 멘토링을 간단히 회고하세요.

# 멘토 코멘트 
## 칭찬할 점
이번 멘토링에서 칭찬할 점을 적어 주세요.

## 노력할 점 
이번 멘토링에서 부족한 점, 더 노력해야 할 점을 적어 주세요.

## 다음 계획 
다음 멘토링 계획을 적어 주세요.

## 그 외
다른 코멘트가 있다면 더 달아 주세요.
```

### 예시 
#### 0304_JS_let과var.md
``` md
# let과 var
## 스코프(Scope)
- 변수와 매개변수(parameter)의 접근성과 생존기간에 영향을 미치는 범위이다.
- 종류
    + 전역 유효범위(Global Scope)
        * 스크립트 내 어느 곳에서든 참조된다.
    + 지역 유효범위(Local Scope)
        * 정의된 함수 안에서만 참조된다. 함수 밖에서는 참조할 수 없다.
- JavaScript 스코프만의 특징
    + 함수 단위의 유효 범위
    + 변수명 중복 허용
    + var 키워드의 생략
        * var 키워드가 생략되면 전역 변수로 선언된다.
    + 렉시컬 특성
        * 함수 실행 시 스코프를 함수 실행 환경이 아닌 함수 정의 환경으로 참조하는 특성이다.

## 호이스팅(hoisting)
변수 선언은 어디에서 하든 코드가 실행되기 전에 처리된다. 이렇게 변수 선언이 함수 또는 전역 코드의 상단에 이동하는 것과 같은 행동이 호이스팅이다. 하지만 끌어올려진 변수들은 undefined를 반환한다. 그렇기에 가능한 함수 상단 근처에 두는 것이 좋다.

## 변수
어떠한 값에 값을 상징하는 변수 이름을 붙이고, 식별자라고 부르며 특정 규칙을 따른다. 문자, 언더바(_), 혹은 달러 기호($)로 시작해야 한다.

## let과 var로 변수 선언
- var
    + 지역 및 전역 변수를 선언하는데 모두 사용될 수 있다.
    + 블록 범위가 정의되지 않았을 때 등장해서 스코프의 영향을 받지 않는다.

            if (true) {
                var x = 5;
            }
            console.log(x); // 5
- let
    + 블록 범위 지역 변수를 선언하는데 사용될 수 있다.
    
            if (true) {
                let y = 5;
            }
            console.log(y); // ReferenceError: y is not defined

## 궁금한 점
1. 블록 범위는 언제 정의됐을까?
    - ES6(ECMAScript 2015)에서 등장했다. `let`과 `const`를 포함한 구조해제 같은 새로운 문법들도 모두 ES6에서 등장했다.

## 회고 
코드를 짤 때 아무것도 모르고 `var`만 썼었는데, 이제는 `let`과 `var`의 차이를 알았으니 `let`을 써야겠다.

# 멘토 코멘트 
## 칭찬할 점
정리를 꼼꼼하게 잘했다

## 노력할 점 
본인이 정리한 것을 보지 못하면 `let`과 `var`의 차이를 설명하지 못한다

## 다음 계획 
자바스크립트 반복문을 가르칠 예정이다

## 그 외
분량이 적었던 것 같다 분량을 더 늘려도 될 것 같다
```

