# React_Study
React 공부

## 🍟 설치법
```bash
npx create-react-app my-app
```
```bash
# typescript 설지
npx create-react-app my-app --template typescript

#npm
npm install typescript @types/node @types/react @types/react-dom @types/jest

#yarn
yarn add typescript @types/node @types/react @types/react-dom @types/jest
```


## 기타 규칙
- return은 소괄호로 감싸준다
```javascript
return(
  <div>태그는 무조건 1개만 return   (= 루트 노드가 무조건 존재)</div>
)
```
- export default 는 마지막에 하거나 선언과 동시에 가능하다.
```javascript
export default function Test(){

}

export default Test;
```

- CSS 따로 적용하고 싶으면 .module.css
```html
<!--파일명 App.module.css-->

import styles from 'App.module.css';

function App(){
  return(
    <div>
      <span className={styles.클래스네임> CSS 테스트
      </span>
    </div>
  )
}

```

### 🍮 함수형 컴포넌트
- function으로 정의하고 **return** 문에 jsx 코드를 반환합니다.
```javascript
import React from "react";
import "./App.css";

function NameBox() {
  const name = "test";
  return <div>{name}</div>;
}

export default NameBox;

// function을 사용하지 않고 화살표 함수로도 활용이 가능합니다.

import React from "react";
import "./App.css";

const NameBox = () => {
  const name = "test";
  return <div>{name}</div>;
};

export default NameBox;
```

### 🙁 클래스형 컴포넌트
- class로 정의하고 render() 함수에서 jsx 코드를 반환합니다.
```javascript
import React, { Component } from "react";

class NameBox extends Component {
  render() {
    const name = "react";
    return <div className="react">{name}</div>;
  }
}

export default NameBox;
```


## ✨ State
- 컴포넌트의 속성 값
```javascript
import { useState } from "react";
const [name, setName] = useState() // 구조 분해 할당
// const[변수명, state를 변경해주는 함수] = useState(기본 state의 초기값) 
// setName(state를 변경해주는 함수가 호출되어 state가 바뀌면 React가 해당 컴포넌트를 다시 랜더링 해줍니다.
```

## 🎉 Props(Properties)
- 상위 페이지에서 하위 컴포넌트로 값을 넘기는 것
- 화면의 업데이트를 하기 위해서 State와 Props를 주로 사용합니다.
```javascript
// 상위 페이지 일부
<Test age = {10}/> // html 문법에 정해진 속성값이 아닌 사용자의 임의의 속성을 만들어서 전달
<Test age = {20}/> // html

// 하위 페이지(컴포넌트)
export default function Test(props){ // 위에서 전달한 props에 전달됩니다.
  
  return(
    <div>
      <span>{props.age}</span> // 10 20 출력
    </div>
  )
}


// 하위 페이지(컴포넌트) - 넘겨받은 props 값을 변경할 수는 없습니다.
export default function Test(props){ // 위에서 전달한 props에 전달됩니다.
   const [age, setAge] = useState(props);
  return(
    <div>
      <button onClick={() =>}
        setAge(age+1);  // 상위 페이지에서 가지고 있는 props는 변경할 수 없으므로 컴포넌트의 state 값을 생성하여 그것을 변경하는 코드
      }/>
    </div>
  )
}
```
