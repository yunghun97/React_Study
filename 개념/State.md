# 😎 State

```
Prop과 State 모두 해당 값이 변경되면 return 값을 변경하여 UI를 변경한다.
Prop, State를 사용하지 않고 변경하면 화면의 값은 바뀌지 않는다.
```

## ❗ Prop과 State 차이점

1. Prop은 컴포넌트를 사용하는 외부자를 위한 데이터
2. State는 컴포넌트를 사용하는 내부자를 위한 데이터

### 설명

```javascript
const _mode = useState("Test");
// console로 찍어서 테스트
console.log(_mode);
// 결과
/* 
0: 'Test',
1: f()
*/
const mode = _mode[0];
const setMode = _mode[1];

// 같은 소스
const _mode = useState("Test");
const mode = _mode[0];
const setMode = _mode[1];
// 간단하게
const [mode, setMode] = useState("Test");
```

```
1. useState('~') 안에 인자는 해당 state의 초기값
2. state의 값은 0번째 index 값으로 읽습니다.
3. state를 바꿀때에는 1번째 index 값(함수)으로 바꿉니다.

```

```javascript
// 잘못된 데이터 변경 -> 데이터는 바뀌지만 화면에는 바뀌지 않는다.

function App() {
  const [mode, setMode] = useState("Test");

  return (
    <div>
      <span
        onChangeMode={() => {
          mode = "WELCOME";
        }}
      ></span>
    </div>
  );
}

// state 활용
function App() {
  const [mode, setMode] = useState("Test");

  return (
    <div>
      <span>
        onChangeMode=
        {(_id) => {
          setMode("Read");
          setId(_id);
        }}>
      </span>
    </div>
  );
}
```
