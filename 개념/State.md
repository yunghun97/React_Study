# ๐ State

```
Prop๊ณผ State ๋ชจ๋ ํด๋น ๊ฐ์ด ๋ณ๊ฒฝ๋๋ฉด return ๊ฐ์ ๋ณ๊ฒฝํ์ฌ UI๋ฅผ ๋ณ๊ฒฝํ๋ค.
Prop, State๋ฅผ ์ฌ์ฉํ์ง ์๊ณ  ๋ณ๊ฒฝํ๋ฉด ํ๋ฉด์ ๊ฐ์ ๋ฐ๋์ง ์๋๋ค.
```

## โ Prop๊ณผ State ์ฐจ์ด์ 

1. Prop์ ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ๋ ์ธ๋ถ์๋ฅผ ์ํ ๋ฐ์ดํฐ
2. State๋ ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ๋ ๋ด๋ถ์๋ฅผ ์ํ ๋ฐ์ดํฐ

### ์ค๋ช

```javascript
const _mode = useState("Test");
// console๋ก ์ฐ์ด์ ํ์คํธ
console.log(_mode);
// ๊ฒฐ๊ณผ
/* 
0: 'Test',
1: f()
*/
const mode = _mode[0];
const setMode = _mode[1];

// ๊ฐ์ ์์ค
const _mode = useState("Test");
const mode = _mode[0];
const setMode = _mode[1];
// ๊ฐ๋จํ๊ฒ
const [mode, setMode] = useState("Test");
```

```
1. useState('~') ์์ ์ธ์๋ ํด๋น state์ ์ด๊ธฐ๊ฐ
2. state์ ๊ฐ์ 0๋ฒ์งธ index ๊ฐ์ผ๋ก ์ฝ์ต๋๋ค.
3. state๋ฅผ ๋ฐ๊ฟ๋์๋ 1๋ฒ์งธ index ๊ฐ(ํจ์)์ผ๋ก ๋ฐ๊ฟ๋๋ค.

```

```javascript
// ์๋ชป๋ ๋ฐ์ดํฐ ๋ณ๊ฒฝ -> ๋ฐ์ดํฐ๋ ๋ฐ๋์ง๋ง ํ๋ฉด์๋ ๋ฐ๋์ง ์๋๋ค.

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

// state ํ์ฉ
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
