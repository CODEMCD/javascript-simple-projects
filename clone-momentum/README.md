# 노마드코더스 아카데미 - 바닐라 JS로 크롬 앱 만들기

## 구현 목록
### 3.1 Making a JS Clock part One
- 브라우저에 현재 시간 출력하기
    - `Date()`

### 3.2 Making a JS Clock part Two
- 1초마다 현재 시각 업데이트하여 출력하기
    - `setInterval()`
- 시,분,초의 형식을 '00'으로 만들기
    - 삼항 연산자 사용

### 3.3 Saving the User Name part One
- **Local Storage**: 자바스크립트의 정보를 로컬에 저장하는 방법
    - `localStorage()`
    - <Key, Value> 형태로 사용
    - 로컬 스토리지는 URL 별로 저장됨(다른 URL의 로컬 스토리지에 접근할 수 없음)
- 태그 보이기/안보이기 기능
    - `.css`에서 `display` 사용


### 3.4 Saving the User Name part Two
- 이름 입력 받기
    - input 태그에서 Enter 입력 시 이벤트 발생
        - 이벤트 추가: `addEventHandler()`
        - 기본 이벤트 막기(submit에서 엔터를 누르면 기본적으로 새로고침됨)
    - 입력된 이름 브라우저에 출력
    - 입력된 이름 로컬 스토리지에 저장


### 3.5 Making a To Do List part One
- 3.4에서와 같이 이름 입력 대신 TODO를 입력할 수 있도록 한다.
- js 파일들의 변수명이 중복되지 않도록 주의한다.
- js파일에서 `createElement()`로 태그를 추가할 수 있다.
- `appendChild()`로 자식 태그에 추가할 수 있다.

### 3.6 Making a To Do List part Two
입력된 TODO 목록을 새로고침 등을 해도 계속 유지하여 출력하기
- TODO 목록을 삭제하려면 그 정보를 알고 있어야 하므로 `TODO` 객체로 관리한다.
    - 각 TODO는 id로 식별한다.
- 브라우저에서 자바스크립트 정보 유지: Local Storage 사용
    - Local Storage의 value는 string 타입만 저장 가능하다.
    - 객체를 저장하려면 **JSON**을 사용한다.
        - object -> string: `JSON.stringify()`
        - string -> object: `JSON.parse()`
- array 타입은 `array.forEach(function...)`로 사용할 수 있다.

### 3.7 Making a To Do List part Three
TODO 삭제 구현하기
- HTML에서 TODO 목록 삭제하기
    - TODO 삭제해야할 타겟 설정하기
    - 해당 버튼의 부모 태그 `<li>`를 찾기: `event.target.parentNode`
    - 부모 `<li>` 태그의 자기 자신 + 자식 태그 삭제: `.removeChild`
- 실제 TODO 객체 삭제하기
    - array 객체의 `filter()` 메서드를 사용하여, 삭제된 id를 필터링한다.
    - 변견된 사항을 적용한다.
        - TODO 목록을 관리하는 array 변경
        - local storage 변경

### 3.8 Image Background
배경 이미지 랜덤으로 출력하기
- 이미지가 완전히 로딩된 다음 출력하도록 한다.
- 이미지 파일 이름은 1... 이다.
    - 자바스크립트 랜덤 함수: `Math.random()`
- 배경 이미지 맨 뒤로 보내기(시계, 글자 등 뒤로 보내기)
    - 이미지 삽입(.js): `body.prepend()`
    - CSS: `z-index: -1;`


### 3.9 Getting the Weather part One (Geolocation)
현재 지역 위치 가져오기
- Navigator API 사용
    - 위도, 경도 데이터 가져오기
- [Weather API](https://openweathermap.org/) key 가져오기
    - 회원가입 필요


### 3.10 Getting the Weather part Two (API)
현재 지역 날씨 가져오기
- 새로고침없이 날씨 데이터 가져오기
    - API server 요청 및 응답 처리: `fetch()`
- API 데이터의 형식은 문서 참고
