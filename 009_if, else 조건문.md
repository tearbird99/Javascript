### 🔖 개요
자바스크립트에서 조건문은 프로그램의 흐름을 제어하는 가장 기본적인 도구이다. 주어진 조건식의 참(true) 또는 거짓(false) 여부에 따라 서로 다른 코드를 실행한다.

---

### ⭐ if 문
가장 단순한 형태. 조건이 참일 때만 블록 내부의 코드를 실행한다.
```javascript
const score = 90;

if (score >= 80) {
  // 조건이 참일 때 실행
  console.log("합격입니다.");
}
```

---

### ⭐ if-else 문
조건이 참일 때와 거짓일 때 각각 실행할 코드를 나눈다. "A 아니면 B"의 구조이다.
```javascript
const isLoggedIn = false;

if (isLoggedIn) {
  console.log("환영합니다!");
} else {
  // 조건이 거짓일 때 실행
  console.log("로그인이 필요합니다.");
}
```

---

### ⭐ else if 문 (다중 조건)
여러 개의 조건을 순차적으로 체크해야 할 때 사용한다. 위에서부터 차례대로 조건을 검사하며, 가장 먼저 참이 되는 블록 하나만 실행하고 나머지는 무시한다.
```javascript
const age = 20;

if (age < 13) {
  console.log("어린이");
} else if (age < 20) {
  console.log("청소년");
} else if (age < 30) {
  console.log("청년");
} else {
  // 위의 모든 조건이 거짓일 때 실행
  console.log("성인");
}
```

---

### 📝 작성 시 주의사항
- 숫자 0, 빈 문자열 "", null, undefined, NaN은 조건식에서 false로 평가된다.
- **중괄호({ }) 생략**: 실행할 코드가 한 줄뿐이라면 중괄호를 생략할 수 있으나, 가독성과 실수 방지를 위해 사용을 권장한다.
```javascript
if (true) console.log("OK");

if (true) {
  console.log("OK");
}
```