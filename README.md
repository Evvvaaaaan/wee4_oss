# HTML Form Practice

HTML Form의 주요 입력 요소를 구성하고 CSS와 JavaScript Validation을 단계적으로 적용한 실습입니다.

## Pages

| 파일 | 내용 |
| --- | --- |
| `index.html` | 실습 페이지를 연결하는 시작 페이지 |
| `form1.html` | HTML Form 구조와 입력 요소 |
| `form1_css.html` | Form 레이아웃과 상태별 CSS 적용 |
| `form1_js.html` | HTML Validation과 JavaScript 제출 처리 |

## Links

- GitHub Repository: https://github.com/2026-2-OSS/assign04-c01-22300404
- Deploy URL: https://wee4-oss.vercel.app/
- Clone coding reference: https://getbootstrap.com/docs/5.2/examples/checkout/
- Visual reference: 과제 진행 중 제공된 결제 Form 이미지
- HTML Form reference: https://www.w3schools.com/html/html_forms.asp
- CSS Form reference: https://www.w3schools.com/css/css_form.asp

## Run

별도의 빌드 과정 없이 `index.html`을 브라우저에서 열어 실행할 수 있습니다.

## Weekly Review

### Key Learning

1. `form`, `label`, `input`, `select`, `textarea`를 조합하여 입력 목적이 명확한 Form을 구성하는 방법을 익혔습니다.
2. CSS Grid와 상태 선택자(`:focus`, `:hover`, `:checked`)를 사용해 Form을 읽기 쉽고 반응형인 UI로 표현했습니다.
3. HTML Constraint Validation API와 JavaScript 제출 이벤트를 함께 사용해 잘못된 입력을 차단하고 유효한 제출을 처리했습니다.

### Form Elements

| 요소 | 용도 |
| --- | --- |
| `input type="text"` | 이름, 우편번호, 카드 번호, 보안 코드 입력 |
| `input type="email"` | 이메일 형식 검사와 이메일 입력 |
| `input type="radio"` | 신용카드와 PayPal 중 하나의 결제 방법 선택 |
| `input type="checkbox"` | 이용약관 동의 확인 |
| `input type="date"` | 생년월일 선택 |
| `select` | 카드 만료 월과 연도 선택 |
| `textarea` | 주문 관련 추가 요청 입력 |
| `fieldset`, `legend` | 관련된 결제 방법과 만료일 입력 요소 그룹화 |
| `button type="submit"` | Form 제출 요청 |

### HTML vs CSS

`form1.html`은 입력 요소의 의미와 연결 관계에 집중한 문서입니다. `form1_css.html`은 같은 HTML 구조에 색상, 배경, 테두리, 간격, 너비, Grid 레이아웃과 반응형 스타일을 추가했습니다. 또한 입력 포커스와 링크·버튼 Hover 상태를 시각적으로 구분했습니다.

### Validation & JavaScript

`form1_js.html`은 필수 입력에 `required`, 이메일에 `type="email"`, 이름에 `minlength="2"`를 적용했습니다. 제출 이벤트에서는 `event.preventDefault()`로 기본 제출을 막고 `checkValidity()`로 전체 Form을 검사합니다. 유효하지 않으면 첫 번째 `:invalid` 요소에 `focus()`를 적용하고 `return`으로 종료합니다. 모든 조건을 만족하면 `alert()`로 등록 완료 메시지를 표시합니다.

### Problem & Solution

초기 Form에는 과제의 필수 요소인 체크박스, 날짜 입력, 텍스트 영역이 없었습니다. 결제 화면의 의미를 유지하도록 약관 동의, 생년월일, 주문 메모 항목을 추가해 해결했습니다. 또한 브라우저의 기본 Validation이 `submit` 이벤트보다 먼저 제출을 막는 문제를 피하기 위해 JavaScript 버전의 Form에 `novalidate`를 적용하고, 이벤트 내부에서 `checkValidity()`와 `reportValidity()`를 직접 호출했습니다.

### Reflection

HTML Validation은 단순한 속성만으로도 많은 입력 오류를 검사할 수 있지만, 사용자에게 일관된 제출 흐름을 제공하려면 JavaScript 이벤트 처리와 함께 동작 순서를 이해해야 한다는 점을 배웠습니다. 다음에는 서버에서도 같은 입력값을 다시 검사하는 방법을 학습하고 싶습니다.

## Weekly Quiz Draft

1. 객관식: Form의 기본 제출 동작을 JavaScript에서 막는 메서드는 무엇인가요?
   - 정답: `event.preventDefault()`
   - 해설: submit 이벤트 객체의 `preventDefault()`를 호출하면 페이지 이동이나 새 요청과 같은 기본 제출 동작이 중단됩니다.
2. OX: `checkValidity()`는 Form 내부의 HTML Validation 조건을 모두 만족하면 `true`를 반환한다.
   - 정답: O
   - 해설: `required`, `type`, `minlength`, `pattern` 등의 제약 조건을 모두 통과하면 `true`를 반환합니다.
