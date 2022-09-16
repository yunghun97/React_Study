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
