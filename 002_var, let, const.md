### 🔖 개요
```javascript
var a = 5;
let b = 5;
const c = 5;
```
ES6(ECMAScript 6) 도입 이래 var은 잘 사용되지 않는 변수 선언식이며, 현재는 주로 let과 const가 사용된다. 이 셋은 **스코프, 재선언/재할당, 호이스팅** 등으로 구분이 가능하다.

---

### ⭐ 특징

#### 🌟 스코프
변수가 살아있는 유효범위를 말한다. var과 let/const를 가르는 가장 큰 기준이 된다.

#### 1. var : 함수 레벨 스코프 (Function-level Scope)
var로 선언된 변수는 **오직 함수 몸체만을 지역 스코프로 인정**한다. 함수 밖에서 선언하면 모두 전역 변수가 된다. 때문에 if문, for문, while문 등 자바스크립트의 일반적인 블록({ }) 안에서 var를 선언해도, 블록을 무시하고 밖으로 튀어나온다는 문제점을 가진다.
```javascript
if (true) {
    var age = 30;
}
console.log(age); // 30 (에러 X. 블록 밖에서도 접근 가능)
```

#### 2. let & const: 블록 레벨 스코프 (Block-level Scope)
반면 보다 현대적인 let과 const는 모든 코드 블록({ })을 지역 스코프로 인정한다. 함수는 물론이고 if, for, try/catch 등의 중괄호 안에서 선언된 변수는 그 안에서만 살다가 블록이 끝나면 사라지게 된다.
```javascript
if (true) {
    let name = "tearbird";
}
console.log(name); // ReferenceError: name is not defined
```
**전역 변수가 많아지면 프로그램의 복잡도가 기하급수적으로 올라간다.** 어디서든 값을 바꿀 수 있기 때문에 디버깅 지옥에 빠지기 쉽다. let과 const를 사용하면 변수를 최대한 좁은 범위(블록)에 가둘 수 있어, 코드의 예측 가능성이 높아진다.

___

#### 🌟 재선언
같은 변수명을 여러 번 쓸 수 있냐, 없냐를 말한다. 

#### 1. var : 재선언 가능
이미 선언된 변수가 있다면, 에러를 내는 대신 기존 변수의 값을 덮어쓰고 새로 할당하는 식으로 작동한다. 이 때문에 코드가 수천 줄이 넘어가는 상황에서, 내가 이전에 userName이라는 변수를 썼다는 사실을 잊고 다시 **var userName = "New User";**라고 선언해 버리면? JS는 아무런 경고도 해주지 않게 된다.
```javascript
var point = 100;
// ... (중략) ...
var point = 200; // 실수로 재선언해도 에러 X
console.log(point); // 200
```

#### 2. let & const : 재선언 불가능
let과 const는 같은 스코프 내에서 중복된 이름의 변수 선언을 절대 허용하지 않는다. 만약 이미 선언된 이름을 다시 사용하려고 하면, 코드를 실행하기도 전에 SyntaxError를 발생시켜 개발자에게 즉각 경고한다. (코드의 무결성 유지 용이)
```javascript
let score = 50;
let score = 100; // Uncaught SyntaxError: Identifier 'score' has already been declared
```

---

#### 🌟 재할당
선언된 변수에 새로운 값을 다시 집어넣는 것을 말한다. var, let은 가능하지만 const는 불가능하다.

#### 1. var & let : 재할당 가능
프로그램 실행 중에 값이 계속 변해야 하는 경우에 사용하며, 메모리에 저장된 기존 값을 지우고 새 값을 덮어쓴다.
```javascript
let score = 10;
score = 20; // 재할당 가능
score = score + 5; // 현재 값에 연산해서 다시 넣기도 가능
```

#### 2. const: 재할당 불가능
const는 'Constant(상수)'의 약자로, 재할당이 절대 불가능하다. 선언과 동시에 값을 넣어야 하며(초기화 필수), 이후에 값을 바꾸려 하면 TypeError가 발생한다.
```javascript
const birthYear = 1995;
birthYear = 2000; // Uncaught TypeError: Assignment to constant variable.
```
※ const로 선언한 배열 혹은 객체의 요소 혹은 프로퍼티는 변경 가능하다.
```javascript
const fruits = ['apple', 'banana']; // const 배열 선언

fruits[0] = 'cherry'; // 1. 요소 변경 (가능)
fruits.push('orange'); // 2. 요소 추가 (가능)
fruits.pop(); // 3. 요소 삭제 (가능)
console.log(fruits); // ['cherry', 'banana']

fruits = ['grape', 'melon']; // 4. 재할당 (불가능 - TypeError)
```
```javascript
const user = {
  name: 'Edery',
  age: 35
};

user.age = 36; // 1. 프로퍼티 값 변경 (가능)
user.isAdmin = true; // 2. 새로운 프로퍼티 추가 (가능)
delete user.name; // 3. 프로퍼티 삭제 (가능)
console.log(user); // { age: 36, isAdmin: true }

user = { name: 'kim' }; // 4. 재할당 (불가능 - TypeError)
```

---

#### 🌟 호이스팅
자바스크립트 엔진은 코드를 실행하기 전, 전체 코드를 훑으며 어떤 변수들이 있는지 미리 파악한다. 이 과정에서 **변수 선언문이 마치 코드의 맨 위로 끌어올려진 것처럼 동작하는 것**을 호이스팅이라고 한다.

#### 1. var의 호이스팅
선언과 동시에 undefined로 초기화까지 같이 일어난다. 그래서 선언하기도 전에 변수를 불러도 에러가 나지 않고 undefined를 출력한다.
```javascript
console.log(a);  // undefined :: 변수 선언 이전에 참조 가능

var a  // 초기화

console.log(a);  // undefined

a = 10  // 할당

console.log(a);  // 10
```

#### 2. let & const의 호이스팅 (TDZ 존재)
분명히 호이스팅은 일어난다. 하지만 var와 달리 초기화가 자동으로 되지 않는데, 이는 let과 const에 **TDZ**가 존재하기 때문이다.
- TDZ(Temporal Dead Zone) : 스코프의 시작 지점부터 초기화 시작 지점까지의 구간. 자바스크립트는 let이나 const로 선언된 변수를 발견하면 메모리에 공간은 확보(호이스팅)하지만, **실제 선언문에 도달하기 전까지는 해당 변수를 사용하지 못하도록 잠금**을 걸어버린다.
```javascript
console.log(a);  // ReferenceError :: 변수 선언 이전에 참조 불가능

let a  // 초기화

console.log(a);  // undefined

a = 10  // 할당

consloe.log(a);  // 10
```

---

### 📝 요약
| 구분 | var | let | const |
| :--- | :---: | :---: | :---: |
| **스코프** | 함수 레벨 | 블록 레벨 | 블록 레벨 |
| **재선언** | 가능 (⭕) | 불가능 (❌) | 불가능 (❌) |
| **재할당** | 가능 (⭕) | 가능 (⭕) | 불가능 (❌) |
| **호이스팅** | undefined 초기화 | TDZ 발생 | TDZ 발생 |
| **권장 사용** | 권장 안 함 | 값이 변할 때 | 상수, 기본값 |