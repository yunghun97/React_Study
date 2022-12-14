# React_Study

React ๊ณต๋ถ

## ๐ ์ค์น๋ฒ

```bash
npx create-react-app my-app
```

```bash
# typescript ์ค์ง
npx create-react-app my-app --template typescript

#npm
npm install typescript @types/node @types/react @types/react-dom @types/jest

#yarn
yarn add typescript @types/node @types/react @types/react-dom @types/jest
```

## ๊ธฐํ ๊ท์น

- return์ ์๊ดํธ๋ก ๊ฐ์ธ์ค๋ค

```javascript
return <div>ํ๊ทธ๋ ๋ฌด์กฐ๊ฑด 1๊ฐ๋ง return (= ๋ฃจํธ ๋ธ๋๊ฐ ๋ฌด์กฐ๊ฑด ์กด์ฌ)</div>;
```

- export default ๋ ๋ง์ง๋ง์ ํ๊ฑฐ๋ ์ ์ธ๊ณผ ๋์์ ๊ฐ๋ฅํ๋ค.

```javascript
export default function Test(){

}

export default Test;
```

- CSS ๋ฐ๋ก ์ ์ฉํ๊ณ  ์ถ์ผ๋ฉด .module.css

```html
<!--ํ์ผ๋ช App.module.css-->

import styles from 'App.module.css'; function App(){ return(
<div>
  <span className="{styles.ํด๋์ค๋ค์"> CSS ํ์คํธ </span>
</div>
) }
```

### ๐ฎ ํจ์ํ ์ปดํฌ๋ํธ

- function์ผ๋ก ์ ์ํ๊ณ  **return** ๋ฌธ์ jsx ์ฝ๋๋ฅผ ๋ฐํํฉ๋๋ค.

```javascript
import React from "react";
import "./App.css";

function NameBox() {
  const name = "test";
  return <div>{name}</div>;
}

export default NameBox;

// function์ ์ฌ์ฉํ์ง ์๊ณ  ํ์ดํ ํจ์๋ก๋ ํ์ฉ์ด ๊ฐ๋ฅํฉ๋๋ค.

import React from "react";
import "./App.css";

const NameBox = () => {
  const name = "test";
  return <div>{name}</div>;
};

export default NameBox;
```

### ๐ ํด๋์คํ ์ปดํฌ๋ํธ

- class๋ก ์ ์ํ๊ณ  render() ํจ์์์ jsx ์ฝ๋๋ฅผ ๋ฐํํฉ๋๋ค.

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

## โจ State

- ์ปดํฌ๋ํธ์ ์์ฑ ๊ฐ

```javascript
import { useState } from "react";
const [name, setName] = useState(); // ๊ตฌ์กฐ ๋ถํด ํ ๋น
// const[๋ณ์๋ช, state๋ฅผ ๋ณ๊ฒฝํด์ฃผ๋ ํจ์] = useState(๊ธฐ๋ณธ state์ ์ด๊ธฐ๊ฐ)
// setName(state๋ฅผ ๋ณ๊ฒฝํด์ฃผ๋ ํจ์๊ฐ ํธ์ถ๋์ด state๊ฐ ๋ฐ๋๋ฉด React๊ฐ ํด๋น ์ปดํฌ๋ํธ๋ฅผ ๋ค์ ๋๋๋ง ํด์ค๋๋ค.
```

# ๐ State

```
Prop๊ณผ State ๋ชจ๋ ํด๋น ๊ฐ์ด ๋ณ๊ฒฝ๋๋ฉด return ๊ฐ์ ๋ณ๊ฒฝํ์ฌ UI๋ฅผ ๋ณ๊ฒฝํ๋ค.
```

## โ Prop๊ณผ State ์ฐจ์ด์ 

![image](https://user-images.githubusercontent.com/71022555/191635421-e3418cd3-c7e3-4ea0-b340-61c93e75536e.png)

1. Prop์ ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ๋ ์ธ๋ถ์๋ฅผ ์ํ ๋ฐ์ดํฐ
2. State๋ ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ๋ ๋ด๋ถ์๋ฅผ ์ํ ๋ฐ์ดํฐ

## ๐ Props(Properties)

- ์์ ํ์ด์ง์์ ํ์ ์ปดํฌ๋ํธ๋ก ๊ฐ์ ๋๊ธฐ๋ ๊ฒ
- ํ๋ฉด์ ์๋ฐ์ดํธ๋ฅผ ํ๊ธฐ ์ํด์ State์ Props๋ฅผ ์ฃผ๋ก ์ฌ์ฉํฉ๋๋ค.

```javascript
// ์์ ํ์ด์ง ์ผ๋ถ
<Test age = {10}/> // html ๋ฌธ๋ฒ์ ์ ํด์ง ์์ฑ๊ฐ์ด ์๋ ์ฌ์ฉ์์ ์์์ ์์ฑ์ ๋ง๋ค์ด์ ์ ๋ฌ
<Test age = {20}/> // html

// ํ์ ํ์ด์ง(์ปดํฌ๋ํธ)
export default function Test(props){ // ์์์ ์ ๋ฌํ props์ ์ ๋ฌ๋ฉ๋๋ค.

  return(
    <div>
      <span>{props.age}</span> // 10 20 ์ถ๋ ฅ
    </div>
  )
}


// ํ์ ํ์ด์ง(์ปดํฌ๋ํธ) - ๋๊ฒจ๋ฐ์ props ๊ฐ์ ๋ณ๊ฒฝํ  ์๋ ์์ต๋๋ค.
export default function Test(props){ // ์์์ ์ ๋ฌํ props์ ์ ๋ฌ๋ฉ๋๋ค.
   const [age, setAge] = useState(props);
  return(
    <div>
      <button onClick={() =>
        setAge(age+1);  // ์์ ํ์ด์ง์์ ๊ฐ์ง๊ณ  ์๋ props๋ ๋ณ๊ฒฝํ  ์ ์์ผ๋ฏ๋ก ์ปดํฌ๋ํธ์ state ๊ฐ์ ์์ฑํ์ฌ ๊ทธ๊ฒ์ ๋ณ๊ฒฝํ๋ ์ฝ๋
      }/>
    </div>
  )
}
```
