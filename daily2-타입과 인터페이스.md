# 데일리 팀 미션

## 1.
## 2. Type과 Interface의 차이점에 대해 정리해주세요
둘다 타입을 정의하는 문법이다. 둘다 객체 타입을 정의할수 있다.
단, 인터페이스는 : 객체 타입을 정의할떄 사용한다.
타입 별칭은 : 특정 타입이나 인터페이스 등을 참조할수 있는 타입 변수인 타입을? 의미한다.

### 인터페이스와 타입의, 객체 정의 방식
```ts
// interface
interface Person {
  name: string;
  age: number;
}
```
```ts
// Type
type Person = {
  name: string;
  age: number;
};
```

타입은 기존 타입(문자열, 숫자, 객체 등)에 별명을 붙이는 '타입 별칭'이기 때문에,  
- 타입 사용이 적합한 경우   
: 반복되는 타입을 변수화해서 쉽게 표기하고 싶을 때.  
: 해당 타입이 어떤 역할을 하는지 이름 짓고 싶을 때.   
*실제 JavaScript로 변환되면 타입 별칭을 만들어둔 코드는 사라진다.(타입은 js실행 시점에는 존재하지 않음)

그래서 객체애 대한 타입을 선언하는건 인터페이스가 더 적합해 보인다..

## 확장 방식에서의 차이 - 인터페이스: extends / 타입: intersection(&)
인터페이스는 상속받아서 타입정의를 확장할 수 있다. - 상속받아서 확장하는 느낌 -- 확장하는 느낌  
타입은 인터섹션으로 타입을 결합한다. - A = B & ... - A이면서 B인 조건을 충족하는걸 통과시킴 -- 타입을 결합해서 조건으로 확장을 흉내내는 느낌..
```ts
interface Person {
  name: string;
  age: string;
}

interface Developer extends Person {
  skill: string;
}

const dove: Developer = {
  name: '도브',
  age: 20,
  skill: 'TypeScript'
};
```
### 선언병합 - 인터페이스: 중복 선언시 내용이 자동 병합됨 / 타입: 중복 선언 불가능

타입별칭은 새로운 속성을 추가하기 위해 & 를 사용한다.
인터페이스처럼 속성을 추가하기 위해 다시 열지는 못한다.
다른것과의 조건으로 덧붙여나가는 방식이다.

결론: 인터페이스는 객체 구조 정의하는데 특화되어있고, 타입은 union(|), 조건부 타입 등 조금 더 다채롭고 복잡한 타입을 커스텀하기 좋음.
<img width="776" alt="Pasted Graphic 23" src="https://github.com/user-attachments/assets/ddc1f937-c72f-475a-b3cc-409e9c19cf74" />

