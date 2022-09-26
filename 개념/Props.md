# 🤔 Props

- 속성

### 기본 텍스트 넘겨주기

```javascript
function Header(props){
    console.log(props) // Object -> title: "Test" 출력
    // 특정 속성만 출력 사용하고 싶을 때
    return(
        <h1>{props.title}</h1>
    )
}

function App(){
    return(
        <div>
            <Header title="Test"></>
        </div>
    )
}

```

### Object 넘겨주기

```javascript
function Header(props){
    console.log(props) // Object -> title: "Test" 출력
    // 특정 속성만 출력 사용하고 싶을 때
    return(
        <h1>{props.title}</h1>
    )
}

function App(){
    const arr = [
    {id:1, title: 'java', body:'java~~'},
    {id:2, title: 'python', body:'c++~~'},
    {id:3, title: 'c++', body:'c++~~'},
]
// 넘겨주려는 값을 {}로 감싸서 남겨준다.
    return(
        <div>
            <Header arr={arr}></>
        </div>
    )
}
```
