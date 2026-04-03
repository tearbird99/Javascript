### 🔖 개요

자바스크립트의 원시 타입(Primitive Type) 중 혼동하기 쉬운 null, undefined와 최근 추가된 symbol에 대해 설명한다.

---

### ⭐ null (명시적, 의도적)
- **의미**: **의도적으로 "값이 없음"을 명시**한 상태
- **발생 상황**: 개발자가 변수에 빈 값을 넣고 싶을 때 직접 할당
- **특징**: 참조를 제거하거나 객체가 없음을 나타낼 때 사용
```javascript
let user = null; // 의도적인 빈 값
console.log(typeof(null)); // object (역사적 버그)
```
자바스크립트가 처음 설계될 때, 의도치 않은 버그로 null이 객체로 분류됨. typeof(null) = object 는 그 잔재.

---

### ⭐ undefined
- **의미**: 값이 할당되지 않은 상태
- **발생 상황**: 변수를 선언만 하고 초기화하지 않았을 때 자바스크립트 엔진이 자동으로 할당
- **특징**: **"데이터가 존재하지 않음"**을 의미하는 엔진의 기본값
```javascript
let name;
console.log(name); // undefined
console.log(typeof(undefined)) // undefined
```
- 초기화되지 않은 변수의 값
- 존재하지 않는 객체 프로퍼티나 배열 요소에 접근했을 때 반환되는 값
- 값을 명시적으로 반환하지 않는 함수의 반환 값
- 전달되지 않은 인자의 값

---

### ⭐ symbol
심볼(symbol)은 ES6에서 도입된 자바스크립트의 7번째 원시 타입이다. 객체의 고유한 프로퍼티 키를 만들기 위해 사용하며, **다른 어떤 값과도 중복되지 않는다**는 점이 핵심이다.

#### 🌟 주요 특징
- **유일무이함**: Symbol()을 호출할 때마다 매번 새로운 고유 값이 생성된다.
```javascript
const s1 = Symbol('id');
const s2 = Symbol('id');
console.log(s1 === s2); // false
```
- **변경 불가능**: 한 번 생성된 심볼 값은 수정할 수 없다.
- **암묵적 형변환 불가**: 문자열이나 숫자로 자동 변환되지 않음. 출력이 필요하면 .toString()을 명시해야 한다.

#### 🌟 사용 목적: 객체의 숨겨진 프로퍼티
객체에 심볼을 키로 사용하면, 일반적인 방법으로는 접근하거나 수정할 수 없는 속성을 만들 수 있다.
- **프로퍼티 은닉**: for...in 루프나 Object.keys() 메서드에서 심볼 키는 노출되지 않는다.
```javascript
const id = Symbol('id');
const user = {
  name: 'Edery',
  [id]: 12345
};

console.log(Object.keys(user)); // ["name"] (id는 안 보임)
```
- **이름 충돌 방지**: 외부 라이브러리에서 가져온 객체에 나만의 속성을 추가하고 싶을 때, 기존 키와 이름이 겹쳐서 덮어씌워지는 사고를 원천 차단한다.

#### 🌟 Symbol 구분법
```javascript
// "mySymbol"이라는 설명을 가진 심볼 생성
const s1 = Symbol("hello");
const s2 = Symbol("hello");

// 1. toString() 호출
console.log(s1.toString()); // Symbol(hello)

// 2. .description (ES2019 이후)
console.log(s1.description); // hello
```