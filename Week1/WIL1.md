모던 자바스크립트 입문 1 ~ 7장을 읽고 필요하다고 생각하는 부분을 정리해보았다.
----

*1장
- 자바스크립트의 특징
    - 인터프리터 언어
    - 동적 프로토타입 기반 객체 지향 언어
    - 동적 타입 언어
    - 함수가 일급 객체임
    - 함수가 클로저를 정의함
- 자바스크립트의 기술적 요소
    - ECMAScript(코어 언어)
    - 클라이언트 측의 고유한 기술 요소
        - Window 인터페이스
        - DOM
        - XMLHttpRequest
    - 서버 측 자바스크립트의 고유한 기술 요소
        - Node.js
        - Rhino
        - Aptana Jaxer

*2장
- 자바스크립트 파일 실행 방법
    - 웹 브라우저 콘솔
    - HTML 문서에 삽입하여 웹 브라우저로 실행
    - Node.js에서 실행
        - Node.js의 대화형 모드로 실행
        - Node.js로 파일을 읽어들여 실행

*3장 </br>
3.1
- Var: 변수를 선언하기 위한 선언자 - 자바스크립트에는 변수 타입이 없다
- 변수를 선언하지 않은 상태에서 값을 대입해도 오류가 나오지 않는다: 자바스크립트 엔진이 자동으로 전역번수 선언 그러나 버그의 원인이 될 수 있음
- 변수 선언의 끌어올림(호이스팅): 프로그램 중간에 변수를 선언하더라도 변수가 프로그램 첫머리에 선언된 것처럼 다른 문장 앞에 생성. 단 선언과 동시에 대입하는 코드는 끌어올리지 않음

3.2
- 동적 타입 언어: 변수에 저장된 데이터 타입을 동적으로 바꿀 수 있는 언어
- 데이터 타입의 분류: 원시 타입, 객체 타입
- 원시 타입: 숫자, 문자열, 논리값, 특수한 값(undefined, null), 심벌
- Undefined: 정의되지 않은 상태
    - 값을 아직 할당하지 않은 변수의 값
    - 없는 객체의 프로퍼티를 읽으려고 시도했을 때의 값
    - 없는 배열의 요소를 읽으려고 시도했을 떄의 값
    - 아무것도 반환하지 않는 함수가 반환하는 값
    - 함수를 호출했을 때 전달받지 못한 인수의 값
- 심벌: 자기 자신을 제외한 그 어떤 값과도 다른 유일무이한 값
    - 심벌의 생성: Symbol()
    - 심벌과 문자열 연결: Symbol.for()
- 템플릿 리터럴
    - 템플릿: 일부만 변경해서 반복하거나 재사용할 수 있는 틀
    - 템플릿 리터럴: 역따옴표로 묶은 문자열
    - 플레이스 홀더: 실제 내용물을 나중에 삽입할 수 있도록 일단 확보한 장소. ${…}

*4장 </br>
4.1
- 객체: 이름과 값을 한 쌍으로 묶은 데이터를 여러 개 모은 것. 연관 배열, 사전이라고도 부름
    - 프로퍼티: 객체에 포함된 데이터 하나(이름과 값의 쌍)
    - 프로퍼티 이름(키): 프로퍼티의 이름 부분
- 객체의 생성: 객체 리터럴 사용, 생성자 함수 사용
    - 객체 리터럴로 객체 생성: 콜론을 사용해 값과 이름 구분, 프로퍼티 값을 읽거나 쓸 때는 마침표 연산자 or 대괄호 연산자
    - 프로퍼티 추가와 삭제: 없는 프로퍼티 이름에 값을 대입하면 새로운 프로퍼티 추가, delete 연산자 사용하면 프로퍼티 삭제
    - In: 객체에 특정 프로퍼티가 있는지 확인할 수 있음, 객체가 가진 프로퍼티와 객체가 상속받은 모든 프로퍼티를 조사함

4.2
- 함수: 일련의 처리를 하나로 모아 언제든 호출할 수 있도록 만들어 둔 것
- 입력 값 = 인수, 출력 값 = 반환값
- 함수 선언문으로 함수 정의
    - Function 키워드 사용
    - return문 다음에는 줄 바꿈 문자를 넣지 않는다
- 인수: 함수를 호출할 때 전달하는 값, 인자: 함수 정의문의 인수
- 함수 선언문의 끌어올림: 자바스크립트 엔진은 변수 선언문과 마찬가지로 함수 선언문을 프로그램의 첫머리로 끌어올린다
- 값의 전달: 인수에 원시 값을 넘기면 그 값 자체가 인자에 전달
- 참조 전달: 인수로 객체를 넘겼을 때 전달되는 값은 참조 값임
- 인수 여러 개를 우아하게 전달하는 방법: 객체의 프로퍼티에 인수를 담아서 넘긴다
- 유효 범위: 변수에 접근할 수 있는 범위
- 어휘적 범위: 프로그램의 구문만으로 유효 범위를 정함 - 자바스크립트도 채택
- 전역 변수: 함수 바깥에서 선언된 변수, 유효 범위는 전체 프로그램
- 지역 변수: 함수 안에서 선언된 변수와 함수 인자, 유효 범위는 변수가 선언된 함수 내부
- 변수의 충돌: 프로그램의 다른 부분에서 선언된 이름이 같은 변수와 충돌하지 않도록 하기 위해 유효 범위가 있음
- 함수 안에서의 변수 선언과 변수 끌어올림: 함수 안의 변수 선언부를 함수의 첫머리로 끌어올린다
- 블록 유효 범위: {} 안에서만 유효함
    - Let: 블록 유효 범위를 갖는 지역 변수를 선언, let문으로 선언한 변수를 끌어올리지 않는다
    - Const: 블록 유효 범위를 가지면서 한 번만 할당할 수 있는 변수(상수)를 선언 - 반드시 초기화해야 함
- 함수 리터럴로 함수 정의: 함수 리터럴은 이름이 없는 함수이므로 익명 함수 또는 무명 함수라고 부름. 함수 리터럴로 정의한 함수는 끌어올리지 않음
- 메서드: 객체의 프로퍼티 중에서 함수 객체의 참조를 값으로 담고 있는 프로퍼티, 메서드를 정의할 때는 프로퍼티 값으로 함수 리터럴을 대입
    - 메서드는 일반적으로 메서드가 속한 객체의 내부 데이터(프로퍼티 값) 상태를 바꾸는 용도로 사용
    - 자바스크립트에서는 메서드가 프로퍼티이다
- 함수 사용의 장점: 재사용 가능, 만든 프로그램을 이해하기 쉬움, 프로그램 수정이 간단해짐

4.3
- 생성자로 객체 생성: new 연산자를 사용
    - 인스턴스: 생성자와 new 연산자로 생성한 객체, 실체라는 뜻을 가진다
    - 생성자의 역할: 객체를 생성하고 초기화, 이름은 같지만 프로퍼티 값이 다른 객체 여러 개를 효율적으로 생성
- 메서드를 가진 객체를 생성하는 생성자: 생성자에서 this.프로퍼티 이름에 함수의 참조를 대입하면 메서드 정의 가능

4.4
- 내장 생성자: 자바스크립트에 처음부터 포함된 생성자. Ex) object, string, number, boolean, array, date 등
- Es6에서 추가된 내장 생성자: symbol, int8array8, map, set 등
- Date 생성자: 날짜와 시간을 표현하는 객체를 생성 - 다양한 메서드를 활용해 날짜와 시간을 간단하게 처리 가능
- Function 생성자: 함수를 생성 - 전역 변수와 자신의 지역 변수만 읽고 쓸 수 있다는 단점이 있음
- 내장 객체(빌트인 오브젝트): 자바스크립트에서 처음부터 사용할 수 있는 객체 ex) 전역 객체, JSON, math, reflect
- 전역 객체: 전역 객체의 프로퍼티는 프로그램의 어느 위치에서나 사용할 수 있음
    - 전역 객체의 프로퍼티: 전역 프로퍼티, 생성자, 전역 함수, 내장 객체
- 자바스크립트 객체의 분류: 네이티브 객체, 호스트 객체, 사용자 정의 객체
    - 네이티브 객체: ECMAScript 사양에 정의된 객체 ex) 내장 생성자로 생성된 객체, JSON, Math, Reflect 등
    - 호스트 객체: ECMAScript에는 정의되어 있지 않지만 자바스크립트 실행 환경에 정의된 객체 ex) 브라우저 객체, DOM에 정의되어 있는 객체, Ajax를 위한 XMLHttpRequest 객체, HTML5의 각종 API 등
    - 사용자 정의 객체: 사용자가 정의한 자바스크립트 코드를 실행한 결과로 생성된 객체

4.5
- 배열 리터럴로 생성하기: 배열 리터럴은 쉼표로 구분한 값을 []로 묶어서 표현. 배열 요소에 매긴 번호는 인덱스라고 부름
- Length 프로퍼티: 배열 요소의 최대 인덱스 값 + 1이 담겨 있음. Length 프로퍼티 값을 배열 길이라고 부름
- Array 생성자로 생성: 배열은 array 생성자로도 생성 가능
- 배열 요소의 참조: 배열 요소에는 모든 타입의 데이터를 할당할 수 있으며 프로그램에서 참조 가능
- 배열은 객체: 자바스크립트의 배열은 array 객체이며 객체로 배열의 기능을 가상으로 흉내낸 것
    - 배열의 요소 번호로 문자열 사용 가능
    - 없는 배열 요소를 읽으려고 시도하면 undefined 반환 -> 객체에 없는 프로퍼티를 읽으면 undefined가 반환
- 배열 요소의 추가와 삭제: 없는 배열 요소에 값을 대입, push 메서드 사용하여 요소를 배열 끝에 추가, delete 연산자를 이용하여 특정 배열 요소 삭제, delete 연산자를 사용해 배열의 요소를 삭제해도 그 배열의 length 프로퍼티 값은 바뀌지 않음
- 희소 배열: 배열에 요소를 추가하거나 제거해서 인덱스가 0부터 시작되지 않는 배열
    - 희소 배열의 길이는 배열 요소의 개수보다 크다
    - 희소 배열이 아닌 배열의 길이는 배열 요소의 개수와 같다
    - 배열 요소가 있는지 확인하는 법: for/in문이나 hasOwnProperty 메서드 이용

*5장 </br>
5.1
- 연산자와 피연산자: a+b에서 +는 연산자이고, a와 b는 피연산자이다.
- 연산자에는 우선순위가 있어 우선순위대로 계산이 처리된다
- 연산자 간 우선 순위가 같은 경우 결합 법칙에 따라 계산이 처리된다
- 부수 효과가 있는 표현식: 변수 값을 바꾸는 표현식 ex) 대입 연산자, 증가 연산자, 감소 연산자, delete

5.2
- 산술 연산자: 피연산자가 숫자인 연산자, 모든 산술 연산은 64비트 부동소수점 연산으로 이루어짐
- 산술 이항 연산자: +, -, *, /, %
    - 주의점 1: 정수까리 나누어도 결과가 부동소수점
    - 2: 나머지 연산자 %의 피연산자는 부동소수점
    - 3: + 연산자는 피연산자 중 하나가 문자열이면 나머지 피연산자를 문자열로 만든다
    - 4: 계산할 수 없는 경우에는 NaN, 산술연산자의 피연산자가 true면 1, false와 null이면 0, undefined면 NaN
- 산술 단항 연산자: ++, —, +, -
- 좌변 값: 대입 연산자의 왼쪽에 둘 수 있는 표현식 ex) 변수, 객체의 프로퍼티, 배열 요소
- 산술 대입 연산자: +=, -=, *= /=, %=
- Math 객체의 프로퍼티와 메서드: e, ln 2, pi, abs, sin, cos 등의 복잡한 연산을 지원
- 부동소수점과 정확도 문제: 자바스크립트의 숫자는 ieee 754로 규정된 64비트 부동소수점
    - 정확도 문제: 숫자를 자릿수가 정해진 부동소수점으로 표현하여 계산하면 오차가 발생
    - 정밀도 손실: 값이 가까운 두 수를 뺄쎔할 떄 정확도 문제 발생

5.3
- 문자열 연결: + 연산자는 피연산자가 모두 문자열이면 문자열로 연결. 피연산자 중 하나가 문자열 또는 문자열로 변환할 수 있는 객체라면 다른 피연산자의 타입을 문자열로 바꾼 다음 연결.
- 문자열을 조작하는 메서드: 문자열을 처리하기 위한 객체 - String 객체
- 래핑: 원시 값을 객체로 변환하는 행위
- String 객체의 주요 메서드: split, substring, toString 등
- 래퍼 객체: 실행하는 순간에 일시적으로 생성되는 String 객체, 사용자에게는 보이지 않고 처리가 끝나면 곧바로 메모리에서 삭제됨.
    - 문자열은 String 객체, 숫자는 Number 객체, 논리값은 Boolean 객체로 변환된다. 단, null과 undefined에는 래퍼 객체가 없다.
- String 생성자의 메서드: length, fromCharcode, fromCodePoint, prototype, raw
- 문자열을 배열로 읽고 쓰기: 문자열을 읽을 때는 charAt 메서드 대신 대괄호 연산자를 사용할 수 있다. 그러나 배열처럼 값을 대입해서 수정할 수는 없다. 써로게이트 페어로 표현하는 문자는 두 개의 배열 요소로 분리한다.
- 써로게이트 페어: 유니코드 U+10000 이상의 코드 포인트 값을 정의하기 위해 2바이트의 인코딩 값을 한 쌍으로 묶은 것

5.4
- 관계 연산자: 두 개의 피연산자를 비교한 결과를 논리값(true/false)로 반환한다. 관계 연산자는 주로 제어 구조에서 조건식을 만들 때 사용한다.
      - ex) ==, !=, ===, !==, <, >, <=, >=
      - 동일 연산자(==): 좌변과 우변의 피연산자가 같은지를 판별한다.
          - 좌우 피연산자의 타입이 같을 때: 값이 같으면 true, 다르면 false로 판정.
          - 좌우 피연산자의 타입이 다를 때: 두 피연산자가 같은 타입이 되도록 타입을 변환한 다음에 다음 규칙에 따라 동일한지 판별함.
              - undefined와 null은 같은 것으로 한다.
              - 한쪽이 숫자고 다른 한쪽이 문자열이면 문자열을 숫자로 변환해서 비교
              - 둘 중에 한쪽이 논리값이면 true는 1, false는 0으로 변환해서 비교
              - 한쪽이 객체고 다른 한쪽이 숫자 또는 문자열이면 객체를 toString이나 valueOf 메서드를 사용해서 원시 타입으로 변환한 다음 비교
              - 앞에 규칙에서 벗어나면 모두 '같지 않음'으로 판정
      - 일치 연산자(===): 피연산자를 평가한 후에 타입을 변환하지 않은 상태의 두 값을 엄격하게 비교. 타입과 값이 모두 같으면 같다고 판정하고 그렇지 않으면 같지 않다고 판정. 단, NaN만큼은 NaN을 포함한 모든 값과 같지 않다고 판정.
  - 논리 연산자: 관계 연산자를 사용하여 만든 논리식과 결합하여 더욱 복잡한 논리를 정의
      - ex) &&, ||, !
      - 피연산자의 평가: 논리 연산자의 피연산자는 논리값이 아니어도 됨. 피연산자가 논리값이 아니면 필요에 따라 타입을 변환.
      - 단락 평가: 첫 번째 피연산자 값이 표현식을 결정하면 두 번째 피연산자를 평가하지 않는 것. && 연산자와 || 연산자는 단락 평가를 한다.

5.5
- 비트 연산: 2진수 숫자의 자리별 값(비트 값)을 다루는 연산.
- 비트 논리 연산자: 비트 값이 0이면 false, 비트 값이 1이면 true로 평가하는 연산자.
    - ex) &, |, ^, ~
- 비트 시프트 연산자: 정수를 2진수 비트 단위로 오른쪽 또는 왼쪽으로 이동시키는(시프트하는) 연산자.
    - ex) <<, >>, >>>
- 비트 연산의 대입 연산자: 산술 연산자와 마찬가지로 비트 연산의 대입 연산자를 사용할 수 있다.

5.6
- typeof 연산자: 단항 연산자이며 피연산자의 데이터 타입을 뜻하는 문자열을 반환. 함수 이외의 객체에 대해 모두 "object"를 반환하므로 객체 유형은 파악할 수 없음. 객체 유형을 조사할 때는 instanceof 연산자와 객체의 constructor 프로퍼티를 사용.
- 조건 연산자(?:): 주어진 조건의 참과 거짓에 따라 값을 선택.
- 쉼표 연산자: 이항 연산자로 왼쪽 피연산자르 평가하고 오른쪽 피연산자를 평가한 이후에 마지막으로 오른쪽 끝 피연산자의 값을 반환.
- eval 함수: 문자열 단 하나만을 인수로 받아서 자바스크립트 코드로 해석. eval 함수를 호출하는 행위는 인수로 받은 문자열을 코드로 바꾸어 eval 함수를 호출한 부분과 맞바꾸겠다는 뜻이다.

5.7
- 숫자를 문자열로 변환
    - 숫자와 문자열을 + 연산자로 연결하면 숫자의 타입이 문자열로 바뀜.
    - Number 객체의 메서드는 숫자의 타입을 문자열로 바꿈.
    - String 생성자 앞에 new 연산자를 붙이지 않으면 일반적인 함수로 활용 가능. 이때 String 함수의 반환값은 String 객체가 아닌 문자열이다.
- 문자열을 숫자로 변환
    - 수식 안에서 묵시적으로 변환: 0을 빼거나 앞에 +를 붙여서 변환
    - parseInt와 parseFloat 함수를 사용: parseInt는 문자열을 정수로 바꾸고 parseFloat는 문자열을 부동소숫점으로 바꾸는 함수.
    - Number 생성자 앖에 new 연산자를 붙이지 않으면 일반 함수로 활용 가능. 이때 Number 함수의 반환값은 Number 객체가 아닌 숫자이다.
- 논리값으로 변환: !!(x) 또는 Boolean(x)

*6장 </br>
6.1
- 대화상자를 표시하는 메서드: window.alert, window.prompt, window.confirm
- 대화상자는 모달 창이다. 대화상자가 떠 있는 중에는 부모 창의 작업이 일시적으로 정지 상태가 되어 부모 창을 조작할 수 없음.
    - alert: 경고 대화상자를 표시. 인수로는 경고 문자열을 받는다.
    - prompt: 입력 대화상자를 표시. 인수로는 입력을 보조하는 문자열을 받는다. 사용자로부터 입력받은 문자열은 prompt 문자열의 반환값이 된다.
    - confirm: 확인 버튼과 취소 버튼이 있는 확인 대화상자를 표시. 인수로는 메시지를 뜻하는 문자열을 받는다. 확인 버튼을 누르면 true가, 취소 버튼을 누르면 false가 반환된다.

 6.2
 - console 객체의 메서드: dir, error, info, log, warn 등
 - 콘솔에 텍스트 출력: log, info, warn, error 메서드를 사용. 로그 시작 부분에 주의 표식을 추가하는 등 로그 스타일이 다르다. %s나 %f 등의 서식 문자열을 두 번째 이후 인수의 값으로 바꾸는 기능이 있다.
 - 객체의 프로퍼티를 목록으로 표시: console.dir 메서드는 객체의 프로퍼티를 나열. 인수로는 객체 하나를 받는다.
 - 타이머: console.time과 console.timeEnd 메서드를 사용해 특정 코드의 실행 시간을 측정할 수 있음. 타이머 이름을 인수로 넘겨 호출하면 처리에 소요된 시간이 밀리초 단위로 표시됨.

6.3
- 이벤트: 사용자가 버튼을 클릭하는 행위처럼 단말기와 애플리케이션이 처리할 수 있는 동작이나 사건을 뜻함.
- 이벤트 주도형 프로그램: 이벤트가 발생할 때까지 기다렸다가 이벤트가 발생했을 때 미리 등록해 둔 작업을 수행하는 프로그램
- 이벤트 처리기: 이벤트가 발생했을 때 실행되는 함수
- 함수를 이벤트 처리기로 등록하는 방법: HTML 요소의 속성으로 등록, DOM 요소의 프로퍼티로 등록, addEventListener 메서드를 사용
- HTML 요소의 속성에 이벤트 처리기 등록
    - 이벤트 처리기 이름: 이벤트 유형. ex) onclick, onmousedown, onkeypress, onfocus, onsubmit 등
    - 이벤트 처리기 속성을 사용해서 이벤트 처리기를 등록하면 HTML 코드와 자바스트립트 코드가 뒤섞이는 단점이 있다.
- DOM에서 가져온 HTML 요소에 이벤트 처리기 지정
    - DOM: 자바스크립트 등의 프로그램이 HTML 요소를 조작할 수 있게 하는 인터페이스.
    - DOM 객체: HTML 문서나 HTML 요소를 가리키는 객체로 자바스크립트를 사용해 HTML 문서를 조작.
        - window: window 객체라고 부르며 웹 브라우저 윈도우 하나 또는 탭 하나를 가리킴.
        - document: Document 객체라고 부르며 HTML 문서 전체를 가리킴. HTML 문서에서 HTML 요소 객체를 가져오거나 HTML 요소를 새로 만드는 등 HTML 문서 전반에 걸친 기능을 제공.
        - 요소 객체: HTML 문서의 요소를 가리키는 객체
    - DOM을 사용해서 이벤트 처리기 등록
        - 전형적인 방법:
          1. window.onload를 사용하여 HTML 문서를 다 읽어 들인 후에 2와 3을 실행한다.
          2. document.getElementById 메서드를 사용하여 특정 id 속성 값을 가진 HTML 요소의 요소 객체를 가져온다.
          3. 요소 객체의 이벤트 처리기 프로퍼티에 이벤트 처리기로 동작할 함수를 등록한다.
        - 자바스크립트가 실행되는 시점: script 요소는 동기 실행(블로킹 실행)되어 script 요소 안의 작업이 끝나기 전까지는 HTML 문서의 해석이 멈춘다.
     


---- 6장 나머지와 7장 내용은 추후 추가하겠습니다. ----
