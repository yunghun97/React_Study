# π§ββοΈ Event

- νΉμ  μν©μ΄ λ°μνμ λ ν΄λΉ μμμ μ€ν

```javascript

function Header(props){
    return(
        // Reactμμ onClick μ½λ°±ν¨μλ‘ μ²« λ²μ§Έμ event κ°μ²΄λ₯Ό λκ²¨μ€λ€.
        <h1 href="/" onClick={function(event){ // <h1 href="/" onClick={(event)=>{
            event.preventDefault(); // aνκ·Έκ° λμνλ κΈ°λ³Έ λμμ λ°©μ§ -> λ¦¬λ‘λ©μ΄ μ λ¨
            props.onChangeMode(); // propsλ‘ μ λ¬ν onChangeMode μμ± μ€ν
        }}>{props.title}</h1>
    )
}



function Nav(Props){
    // νλΌλ―Έν° 1κ°λ©΄ Arrow ν¨μμμ κ΄νΈ μλ΅ κ°λ₯ evenet =>{}
    <a id='asd' href={'/helloWorld'} onClick={(event)=>{
       props.onChangeMode(event.target.id);
    }}>λ§ν¬</a>
};


function App(){
    const arr = [
    {id:1, title: 'java', body:'java~~'},
    {id:2, title: 'python', body:'c++~~'},
    {id:3, title: 'c++', body:'c++~~'},
    ]


    return(
        <div>
            <Header arr={arr} onChageMode={()=>{ // Headerκ° λ³κ²½λλ©΄ function ν¨μ λ΄λΆμ μλ μμμ μ€νν©λλ€.
                alert('ν€λκ° λ³κ²½λμμ΅λλ€~');
            }}></>
            <Nav topics={topics} onChageMode={(id)=>{
                alert(id);
            }}></Nav>
        </div>
    )
}
```
