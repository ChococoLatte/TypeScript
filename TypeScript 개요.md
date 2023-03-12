## 1. TypeScript(타입스크립트)란?

자바스크립트에 타입을 부여한 언어로 자바스크립트의 확장된 언어라고 볼 수 있다.
타입스크립트는 자바스크립트와 달리 브라우저에서 실행하려면 파일을 한 번 변환해주어야 한다.
이 과정을 **컴파일(compile)**이라고 한다.

- 타입 스크립트는 자바스크립트의 상위집합이다. 다시말해, 모든 자바스크립트 프로그램은 이미 타입스크립트 프로그램이다. 반대로, 타입스크립트는 별도의 문법을 가지고 있기 때문에 일반적으로는 유효한 자바스크립트 프로그램이 아니다.
- 타입스크립트는 리액트와 달리 자바스크립트 라이브러리가 아니기 때문에 자바스크립트의 기존 기능을 기반으로 새로운 기능을 만들거나 기능을 확장하지 않는다.
- 정적 타입(statically Typed)의 특징을 갖는다.
=> 자바스립트는 동적 타입 언어

### 1-(1). 타입스크립트를 사용하는 이유

- 에러 사전 방지 가능
오류가 어디서 발생했는지 찾을 수 있고, 해결책도 올바르게 알려준다.
 
- 코드 가이드 및 자동 완성(개발 생산성 향상)

### 1-(2). 타입스크립트 기본 정리

변수를 만들 때 타입 지정이 가능하다. 
**변수명: 타입명**으로 사용한다.
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

```Typescript
let name: string = 'kim'
```

- Array

타입이 배열인 경우 아래와 같이 선언한다.

```Typescript
let arr:number[] = [1,2,3];
```

- Any

모든 타입에 대해 허용한다는 의미

```TypeScript
let num: any = 10;
```

-any 타입을 사용하면 타입 체커와 타입스크립트 언어 서비스를 무력화시켜버린다. any 타입은 진짜 문제점 을 감추며, 개발 경험을 나쁘게 하고, 타입 시스템의 신뢰도를 떨어뜨리므로 최대한 사용을 피하도록 한다.

-타입 추론

* TypeScript에서 명시적인 타입 표기가 없을 때 타입 정보를 제공하기 위해 사용되는 것

```Typescript
let course = "react - The Complete Guide";
```

-유니온 타입
* TypeScript의 핵심 기능 중 하나로, 값과 타입을 좀 더 유연하게 정의할 수 있게 해준다.
* 변수에 여러가지 타입의 데이터가 들어올 수 있다면 | 기호를 이용해 or 연산자를 표현할 수 있다.

```Typescript
let 이름 :string | number = 'kim'
```

-타입 별칭(Type Alias)
* 우리가 직접 기본 타입을 만들어 거기에 복잡한 타입을 정의해두고 그 타입 별칭을 사용하는 것
* 코드가 간결해지고 관리하기도 수월해진다.

```Typescript
type NameType= string | number;
let 이름 :NameType = 'kim';
```

-제네릭(Generics)

* 타입을 마치 함수의 파라미터처럼 사용하는 것을 의미
* Generic은 자료형을 정하지 않고 여러 타입을 사용할 수 있게 해준다.
* 즉, 선언 시점이 아니라 생성 시점에 타입을 명시하여 하나의 타입만이 아닌 다양한 타입을 사용할 수 있도록
하는 기법이다. 한 번의 선언으로 다양한 타입에 '재사용'이 가능하다는 장점이 있다. 
* 또한 제네릭을 사용하게 되면 따로 타입 변환을 할 필요가 없어서 프로그램의 성능이 향상되는 장점이 있다.

```Typescript
function insertAtBeginning<T>(array: T[],value:T){
  const newArray = [value,...array];
  return newArray;
}

const demoArray = [1,2,3];
const updatedArray = insertAtBeginning(demoArray,-1); // [-1,1,2,3]
const stringArray = insertAtBeginning(['a','b','c'],'d');
```

## 2. 함수 선언

parameter와 return 값에 대해 타입 선언을 할 수 있다.
타입을 사용할 때는 매개변수의 타입뿐만 아니라 반환 값의 타입도 생각해야 한다.

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
