### 🔖 개요
```javascript
let arr1 = [1, 'Hello', 3.14, true, null];
```
배열(Array)은 순서가 있는 데이터(요소)들의 목록이라 할 수 있는 자료구조이다. 자바스크립트에서는 하나의 배열 속 다양한 타입의 데이터를 담을 수 있다.

---

### ⭐ 선언
#### 🌟 배열 리터럴
가장 일반적이고 권장되는 방식이다. 대괄호([])를 사용하여 직관적으로 선언한다.
```javascript
const emptyArr = []; // 빈 배열 생성
const fruits = ['apple', 'banana', 'cherry']; // 초깃값이 있는 배열 생성
const mixedArr = [1, 'Hello', true, { id: 1 }]; // 다양한 타입 혼합
```

#### 🌟 Array 생성자
new Array() 문법을 사용한다. 인자의 개수에 따라 동작이 달라진다.
JavaScript
```javascript
const arr1 = new Array(); // 빈 배열 생성 (인자 없음)
const arr2 = new Array(5); // 길이가 정해진 빈 배열 (인자 하나 = 배열 길이)

// 인자가 여러 개인 경우: 인자들을 요소로 갖는 배열 생성
const arr3 = new Array('A', 'B', 'C'); // ['A', 'B', 'C']
```

---

### ⭐ 배열 요소 접근 및 수정
인덱스를 사용하여 특정 위치의 데이터를 읽거나 변경한다.
```javascript
const colors = ['red', 'green', 'blue'];

// 요소 읽기
console.log(colors[0]); // 'red'
console.log(colors[2]); // 'blue'

// 요소 수정
colors[1] = 'yellow';
console.log(colors); // ['red', 'yellow', 'blue']

// 배열 길이 확인
console.log(colors.length); // 3
```