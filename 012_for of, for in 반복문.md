### 🔖 개요
자바스크립트에서 배열이나 객체의 요소를 간편하게 순회하기 위해 사용되는 반복문에는 **for of 문**과 **for in 문**이 있다. 두 문법은 언뜻 비슷해 보이지만, 대상과 반환값에서 차이를 보인다.

---

### ⭐ for...of 문 (배열 및 iterable 객체용)
for...of는 **배열, 문자열, Map, Set 등 반복 가능한(Iterable) 객체의 값(Value)**을 직접 가져올 때 사용한다.
- **특징**: 인덱스가 아닌 실제 데이터 값을 순차적으로 반환
- **대상**: Array, String, Map, Set, TypedArray 등
```javascript
const fruits = ['apple', 'banana', 'cherry'];

for (const fruit of fruits) {
  console.log(fruit); 
}
// 출력: apple, banana, cherry
```

---

### ⭐ for...in 문 (객체의 프로퍼티용)
for...in은 객체의 모든 열거 가능한(Enumerable) 속성을 순회한다. 주로 **객체의 키 또는 배열의 인덱스를 가져올 때 사용**한다.
- **특징**: 키(프로퍼티)를 반환하며, 배열에 사용할 경우 인덱스 번호를 가져온다. (다만 인덱스 번호가 문자열로 나와 배열에서는 잘 사용되지 않는다.)
- **대상**: 모든 객체
```javascript
const user = {
  name: 'Edery',
  age: 25,
  role: 'developer'
};

for (const key in user) {
  console.log(`${key}: ${user[key]}`); 
}
// 출력
// name: Edery
// age: 25
// role: developer
```

---

### 📚 요약
- 배열의 데이터를 하나씩 꺼내고 싶다면 👉 for...of
- 객체의 키(프로퍼티)들을 훑어보고 싶다면 👉 for...in