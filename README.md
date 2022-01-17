# typescript-training

## 기본 개념
 - 타입이 입혀진 자바스크립트
 - 좀더 견고하고 안전한 코드를 작성할수있다.
 - 자동완성과 오류표시로 작업의 효율성이 높아진다.

## Basic

### 기본타입

### 함수

### 인터페이스

### 이넘

### 연산자를 이용한 타입 정의

### 클래스

### 제네릭

### 타입추론

### 타입호환

### 타입 별칭

## Advanced

### 유티리티 타입
- 코드를 간결하게해준다
- 내장된 타입써도 되고, 클래스나 인터페이스, 제네릭 유니언 타입들로 줄일수도 있다.
- Partial, Pick, Omit

### 맵드 타입
- 기존의 타입을 새로운 타입으로 반환해주는 문법

``` bash
{ [ P in K ] : T }
{ [ P in K ] ? : T }
{ readonly [ P in K ] : T }
{ readonly [ P in K ] ? : T }
```
## 적용 셋업
- .js 파일에서 jsDoc 사용 => 불필요한 코드가 늘어나고 재활용하기 어렵다.
- 타입스크립트 적용
  - npm 초기화 `npm init -y`
  - 타입스크립트 라이브러리 설치 `npm i typescript --save-dev`
  - 타입스크립트 설정 파일 생성 및 기본 값 추가 `tsconfig.json`
```bash
{
  "compilerOptions": {
    "allowJs": true,
    "target": "ES5",
    "outDir": "./built",
    "moduleResolution": "Node",
    "lib": ["es2015", "DOM", "DOM.Iterable"],
    "noImplicitAny": true
  },
  "include": ["./src/**/*"],
}
```
  - 자바스크립트 파일을 타입스크립으로 변환
  - script수정
```bash
  "scripts": { 
    "build": "tsc"
  },
```
  - `tsc`명령어로 타입스크립트 변환
  - 컴파일 타입 에러와 런타임 동작 에러는 별개

## 적용 절차
  - 명시적 `any` 선언하기
    - `tsconfig.json` 파일에 `noImplicitAny`값을 `true`로 추가
  - 함수 파라미터에 `any` 타입적용하기 (생략가능)
  - DOM관련 타입 구체화 
    - 파라미터는 대부분 string
    - Elememt | HTMLElement | HTMLParagraphElement... 상황에 맞는 HTMLElement 적어주면 됨
    - as 타입으로 타입호환으로 타입오류 해결...
  - 내장 api들은 이미 타입추론이 되어있음
  - API함수 타입 구체화

## 환경 (프로젝트 구성)
  - 