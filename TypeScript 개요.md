## 1. TypeScript(타입스크립트)란?

자바스크립트에 타입을 부여한 언어로 자바스크립트의 확장된 언어라고 볼 수 있다.
타입스크립트는 자바스크립트와 달리 브라우저에서 실행하려면 파일을 한 번 변환해주어야 한다.
이 과정을 `컴파일(compile)`이라고 한다.

- 타입 스크립트는 자바스크립트의 상위집합이다. 다시말해, 모든 자바스크립트 프로그램은 이미 타입스크립트 프로그램이다. 반대로, 타입스크립트는 별도의 문법을 가지고 있기 때문에 일반적으로는 유효한 자바스크립트 프로그램이 아니다.

### 1-(1). 타입스크립트를 사용하는 이유

- 에러 사전 방지 가능
오류가 어디서 발생했는지 찾을 수 있고, 해결책도 올바르게 알려준다.
 
- 코드 가이드 및 자동 완성(개발 생산성 향상)

### 1-(2). 타입스크립트 기본 정리

변수를 만들 때 타입 지정이 가능하다. 
`변수명: 타입명`으로 사용한다.

-> 위와 같이 :을 이용하여 자바스크립트 코드에 타입을 정의하는 방식을 타입 표기(Type Annotation)이라고 한다.

 
-타입스크립트 기본 타입:

Boolean
Number
String
Object
Array
Tuple
Enum
Any
Void
Null
Undefined
Never


- String
```TypeScript
let name: string = 'kim'
```

- Array

타입이 배열인 경우 아래와 같이 선언한다.

```TypeScript
let arr:number[] = [1,2,3];
```

- Any

모든 타입에 대해 허용한다는 의미

```Typescript
let num: any = 10;
```

-any 타입을 사용하면 타입 체커와 타입스크립트 언어 서비스를 무력화시켜버린다. any 타입은 진짜 문제점
을 감추며, 개발 경험을 나쁘게 하고, 타입 시스템의 신뢰도를 떨어뜨리므로 최대한 사용을 피하도록 한다.

-변수에 여러가지 타입의 데이터가 들어올 수 있다면 | 기호를 이용해 or 연산자를 표현할 수 있다.

```Typescript
let 이름 :string | number = 'kim'
```

-type 키워드를 이용해 타입을 변수처럼 담아서 사용가능하다.

```Typescript
type NameType= string | number;
let 이름 :NameType = 'kim';
```

## 2. 함수 선언

parameter와 return 값에 대해 타입 선언을 할 수 있다.

```Typescript
function sum(a:number, b:number) : number=>{
  return a+b;
}
```
 

- optional parameter일 경우 ?를 사용한다.

```Typescript
function sum(a:number, b?:number):number=>{
  return a+b;
}

sum(10,20) // 30
sum(10) // 타입 에러 없음
```

참고: https://joshua1988.github.io/ts/guide/interfaces.html#%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4 
이펙티브 타입스크립트
