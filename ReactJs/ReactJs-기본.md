## Keyword
`ReactJs` `jsx`

## Reference
- [노마드 코더 ReactJS로 영화 웹 서비스 만들기](https://nomadcoders.co/react-for-beginners/lobby)

## 개념
#### React란
  > 자바스크립트 라이브러로 인터페이스 생성을 위해 사용된다.   
  > UI를 만드는 엔진이다.

#### React-DOM
  > React Element를 HTML요소로 바꿔주는 역할을 한다.

#### Babel
 > 자바스크립트 컴파일러로 최신 자바스크립트 문법 등 브라우저가 이해하지 못하는 문법을 이해할 수 있도록 변환한다.

#### JSX
 > 자바스크립드를 확장한 문법으로 React와 함께 사용된다.

---------
## React 사용 이유
### 일반 HTML, JavaScript 사용
```
<!DOCTYPE html>
<html lang="en">
    <body>
        <span>Total clicks: 0</span>
        <button id="btn">Click me</button>
    </body>
    <script>
        let counter = 0;
        const button = document.querySelector("#btn");
        const span = document.querySelector("span");
        function handleClick() {
            counter += 1;
            span.innerText = `Total clicks: ` + counter;
        }
        button.addEventListener("click", handleClick);
    </script>
</html>
```

### React 사용
```
<!DOCTYPE html>
<html lang="en">
    <body>
        <div id="root"></div>
    </body>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
        const root = document.getElementById("root");
        const h3 = React.createElement(
            "h3",
            {
                key: "h3",
                onMouseEnter: () => console.log("mouse enter"),
            },
            "Hello, I'm a span"
        );

        const btn = React.createElement(
            "button",
            {
                key: "btn",
                onClick: () => console.log("im clicked"),
            },
            "Click me"
        );
        const container = React.createElement("div", null, [h3, btn]);

        ReactDOM.render(container, root);
    </script>
</html>
```

### React, JSX 사용
```
<!DOCTYPE html>
<html lang="en">
    <body>
        <div id="root"></div>
    </body>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
        const root = document.getElementById("root");
        
        const Title = () => (
            <h3 id="title" onMouseEnter={() => console.log("mouse enter")}>
                Hello I'm a title
            </h3>
        );

        const Button = () => <button onClick={() => console.log("im clicked")}>Click me</button>;
       
        const Container = () => (
            <div>
                <Title /> <Button />
            </div>
        );
        
        ReactDOM.render(<Container />, root);
    </script>
</html>

```

---------
## 정리
  > React 및 JSX를 사용할 경우 컴포넌트가 다른 컴포넌트를 포함하는 구조를 가진다.


