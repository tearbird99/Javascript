### 🔖 개요
자바스크립트 타입은 **기본 타입**과 **객체 타입** 둘로 나뉜다. 이 중 기본 타입의 숫자(number), 문자열(string), 불리안(boolean)을 이 포스트에서 알아볼 것이다.

---


### ⭐ 숫자(Number)

#### 🌟 정수 리터럴
자바스크립트 프로그램에서 10진 정수는 연속된 숫자로 표현한다.
```javascript
let num1 = 0;
let num2 = 10;
let num3 = 100;
```
뿐만 아니라 2진수, 8진수, 16진수도 정수 리터럴 방식으로 선언할 수 있다.
```javascript
let numBin = 0b11; // 1*2 + 1 = 3
let numOct = 0o77; // 7*8 + 1 = 57
let numHex = 0xff; // 15*16 + 15 = 255
```

#### 🌟 부동 소수점 리터럴
```javascript
let pi = 3.14;
```

#### 🌟 산술 연산
여타 대부분의 언어와 같이 덧셈(+), 뺄셈(-), 곱셈(*), 나눗셈(/), 나머지(%) 기호 사용. 다만 자바스크립트에서는 숫자를 0으로 나눠도 에러가 발생하지 않고, 양/음의 무한대를 반환한다. (0 나누기 0 제외 = NaN) 
```javascript
let a = 0 / 0; // NaN
let b = 123 + undefined; // NaN
let c = typeof(b); // number
```

---

### ⭐ 문자열(String)

#### 🌟 문자열 리터럴
```javascript
let str1 = 'Hello,';
let str2 = "World!";
let str3 = `${str1} ${str2}`; // Hello, World!
let str4 = str1 + str2; // Hello,World!
```
백틱(`)으로 감싼 문자열은 문자열 리터럴 안에 자바스크립트 표현식(${})을 넣을 수 있다.

---

### ⭐ 불리안(Boolean)
참(true), 거짓(false)를 나타내는 타입.
```javascript
0 == 0; // true
0 == 1; // false
const truthy = true;

if (truthy) {
  console.log("참"); // 참
}
```