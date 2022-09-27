# 🧙‍♀️ Event

- 특정 상황이 발생했을 때 해당 작업을 실행

```javascript

function Header(props){
    return(
        // React에서 onClick 콜백함수로 첫 번째에 event 객체를 넘겨준다.
        <h1 href="/" onClick={function(event){ // <h1 href="/" onClick={(event)=>{
            event.preventDefault(); // a태그가 동작하는 기본 동작을 방지 -> 리로딩이 안 됨
            props.onChangeMode(); // props로 전달한 onChangeMode 속성 실행
        }}>{props.title}</h1>
    )
}



function Nav(Props){
    // 파라미터 1개면 Arrow 함수에서 괄호 생략 가능 evenet =>{}
    <a id='asd' href={'/helloWorld'} onClick={(event)=>{
       props.onChangeMode(event.target.id);
    }}>링크</a>
};


function App(){
    const arr = [
    {id:1, title: 'java', body:'java~~'},
    {id:2, title: 'python', body:'c++~~'},
    {id:3, title: 'c++', body:'c++~~'},
    ]


    return(
        <div>
            <Header arr={arr} onChageMode={()=>{ // Header가 변경되면 function 함수 내부에 있는 작업을 실행합니다.
                alert('헤더가 변경되었습니다~');
            }}></>
            <Nav topics={topics} onChageMode={(id)=>{
                alert(id);
            }}></Nav>
        </div>
    )
}
```
