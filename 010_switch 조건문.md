### 🔖 개요
switch 문은 하나의 변수나 표현식을 여러 개의 값과 비교하여, 일치하는 조건에 따라 서로 다른 코드를 실행하는 분기 처리 도구이다. if-else if 문이 길어질 때 가독성을 높이기 위해 주로 사용한다.

---

### ⭐ 기본 구조
switch 문은 표현식을 평가한 뒤, 그 결과와 일치하는 case 라벨을 찾아 실행한다.
```javascript
switch (표현식) {
  case 값1:
    // 표현식 === 값1 일 때 실행할 코드
    break;
  case 값2:
    // 표현식 === 값2 일 때 실행할 코드
    break;
  default:
    // 어떤 case와도 일치하지 않을 때 실행할 코드 (선택 사항)
}
```

---

### ⭐ 주요 구성 요소

- **case**: 비교할 값을 명시함. 내부적으로 **일치 비교(===)**를 수행하므로 값뿐만 아니라 데이터 타입까지 같아야 한다.
- **break**: 현재의 switch 블록을 빠져나오게 함. 만약 break를 생략하면 다음 case의 코드까지 연달아 실행되는 폴스루(Fall-through) 현상이 발생한다.
- **default**: if 문의 else와 같은 역할임. 일치하는 case가 없을 때 마지막으로 실행된다.

---

### ⭐ 예시: 요일 판별
```javascript
const day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = "월요일";
    break;
  case 2:
    dayName = "화요일";
    break;
  case 3:
    dayName = "수요일";
    break;
  default:
    dayName = "주말 혹은 알 수 없는 날";
}

console.log(dayName); // "수요일"
```