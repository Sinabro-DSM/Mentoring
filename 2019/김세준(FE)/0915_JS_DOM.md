# Javascript - DOM



## 1. DOM 이란?

#### DOM = The Document Object Model = 문서 객체 모델 

##### 1.1 HTML 문서 내의 각요소에 접근 / 수정

- DOM은 프로그래밍 언어가 **HTML, XML, SVG 같은 웹 문서에 접근**할 수 있는 방법을 제공한다.

- DOM 은 동일한 **문서를 표현하고, 저장하고, 조작하는 방법을 제공**하고 자바스크립트와 같은 스크립팅 언어를 이용해 DOM 을 동적이게 수정할 수 있다.

  

##### 1.2 HTML 문서에 대한 모델 구성

- DOM은 구조화된 nodes와 프로퍼티(property)와 메소드(method)를 가지고 있는 객체로 표현한다.
- DOM 트리는 브라우저가 HTML 문서를 로드한 후 파싱하여 생성하는 모델을 의미한다. 객체의 트리로 구조화되어 있어 DOM tree라 한다.
- DOM tree는 
  - 문서 노드, 요소 노드, 어트리뷰트 노드, 텍스트 노드로 이루어진다.



## 2. DOM 활용



### 2.1 DOM Query 선택



### 2.1.1 노드 하나 선택하기 (Query)

- `document.getElementById('요소의 id')` 

- `document.querySelector('요소 노드') ` 요소가 복수일 경우 첫번째 요소 하나만 반환한다

  

#### 2.1.2 노드 여러개 선택하기 (Query)

- `document.getElementsByClassName('요소의 class') ` 
- `document.getElementsByTagName('요소의 tag')`
- `document.querySelectorAll('요소 노드')`

1번째와 2번째 방법은 HTMLCollection(live) 를 반환한다. 실시간으로 변하는 데이터이기 때문에 배열로 바꿔 노드를 조작하는 방법을 사용하길 권장한다.

```javascript
const elems = document.getElementsByClassName('red');

console.log([...elems]); // [li#one.red, li#two.red, li#terr]

[...elems].forEach(elems => elems.className = 'blue') 
// class가 red인 요소의 class를 blue로 바꾼다
```



### 2.2 DOM Traversing 탐색



#### 2.2.1 parentNode

``` javascript
const elem = document.querySelector('#two');

elem.parentNode.className = 'blue';
```

- 부모 노드를 반환한다.

  

#### 2.2.2 firstChild, lastChild

- 생각대로 작동하지 않는 경우가 있으니 아래의 것을 이용하자



#### 2.2.3 firstElementChild, lastElementChild 

```javascript
const elem = document.querySelector('ul');

elem.firstElementChild.className = 'blue';
elem.lastElementChild.className = 'blue';
```

- firstElementChild: 첫번째 자식 노드를 반환한다.
- lastElementChild: 마지막 자식 노드를 반환한다.



#### 2.2.4 기타 등등 

`hasChildNodes()`

- 자식 노드가 있는지 확인하고 Boolean 값을 반환한다.

  

`childNodes`

- 자식 노드의 모든 것(NodeList)을 반환한다. (텍스트 요소 포함)



`children`

- 자식 노드의 모든 것(HTMLCollection)을 반환한다. (Element type 요소만)



`previousSibling, nextSibling`

- 모든 형제 노드를 탐색한다.   (텍스트 노드 포함)

`previousElementSibling, nextElementSilbing`

- 형제 노드 중에서 Element type 요소만을 탐색한다.



### 2.3 DOM Manipulation 조작



#### 2.3.1 nodeValue 

```javascript
const dom = document.querySelector('#dom');
const domText = dom.firstChild;

console.log(domText.nodeValue); // document
domText.nodeValue = 'DOM';

```

- 이처럼 부모노드 -> 텍스트노드 순으로 탐색하여 nodeValue 프로퍼티로 텍스트 노드를 조작할 수 있다.



#### 2.3.2 textContent

 ```html
<div>
    <h1>Cities</h1>
    <ul>
        <li id="one" class="red">Seoul</li>
        <li id="two" class="red">London</li>
        <li id="three" class="red">Newyork</li>
        <li id="four">Tokyo</li>
    </ul>
</div>
<script>
	const ul = document.querySelector('ul');
    console.log(ul.textContent);
    /*
    	Seoul
    	London
    	Newyork
    	Tokyo
    */
    
    const one = document.querySelector('#one');
    console.log(one.textContent); // Seoul
    
    one.textContent += ', Korea';
    console.log(one.textContent); // Seoul, Korea
    
    one.textContent = `<h1>지역<h1>`;
   	console.log(one.textContent); // <h1>지역</h1>
</script>
 ```

- 텍스트를 추가 또는 변경시에 사용한다.

#### 2.3.3 DOM 조작 방식

- innerHTML 프로퍼티로 콘텐츠를 추가하는 것을 대신하는 방법이다.

```javascript
const newElement = document.createElement('li');
// 요소 노드 생성
const newText = document.createTextNode('이것은 텍스트 노드');
// 텍스트 노드 생성
newElement.appendChild(newText);
// 요소 노드에 텍스트 노드 추가 (마지막 요소로 추가된다)

```



## 궁금한 점



## 회고 

DOM api를 자세하게 공부 할 수 있었고 여러개의 노드를 탐색하는 법을 알았고 innerHTML(), insertAdjacentHTML() 프로퍼티가 보안 취약점이 있다는 걸 깨달았다.

# 멘토 코멘트 

## 칭찬할 점

이번 멘토링에서 칭찬할 점을 적어 주세요.

## 노력할 점 

이번 멘토링에서 부족한 점, 더 노력해야 할 점을 적어 주세요.

## 다음 계획 

다음 멘토링 계획을 적어 주세요.

## 그 외

다른 코멘트가 있다면 더 달아 주세요.