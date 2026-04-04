### 🔖 개요
객체(Object)는 자바스크립트에서 **키(key)-값(value)**로 구성된 데이터의 집합이다. 키는 문자열 또는 심볼, 값은 데이터 타입 상관없이 사용 가능하다. 키를 다른 말로 **프로퍼티**라고도 부른다.

---

### ⭐ 생성
#### 🌟 객체 리터럴
가장 일반적인 방식이다.
```javascript
const user = {
  name: 'Edery',         // 프로퍼티
  age: 25,               // 프로퍼티
  greet: function() {    // 메서드
    console.log('Hello!');
  }
};
```

#### 🌟 생성자 함수 Object()
```javascript
const user = new Object();	// Object 함수로 생성
user.name = 'Edery';		// 프로퍼티 추가
user.age = 25;				// 프로퍼티 추가
user.greet = function() {    // 메서드 추가
    console.log('Hello!');
};
```

#### 🌟 class 키워드 (ES6 이후)
```javascript
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log('Hello!');
  }
}

const user = new User('Edery', 25);
```

---

### ⭐ 프로퍼티 접근 및 수정
- **마침표 표기법 (.)**: 가장 많이 사용하며 식별자 규칙을 따를 때만 가능
- **대괄호 표기법 ([])**: 키 이름에 공백이 있거나, 변수를 키로 사용할 때 필수적
```javascript
const person = { name: 'Lee' };

// 1. 읽기
console.log(person.name);    // 'Lee'
console.log(person['name']); // 'Lee'

// 2. 추가 및 수정
person.age = 20;             // 신규 추가
person['name'] = 'Park';     // 기존 수정

// 3. 삭제
delete person.age;           // age 프로퍼티 삭제
```