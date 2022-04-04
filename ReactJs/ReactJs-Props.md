## Keyword
`ReactJs` `Props`

## Reference
- [노마드 코더 ReactJS로 영화 웹 서비스 만들기](https://nomadcoders.co/react-for-beginners/lobby)
- [React 공식문서](https://ko.reactjs.org/docs/faq-state.html)

## 개념
#### Props
  > 상위 컴포넌트에서 하위 컴포넌트로 전달하는 값이다.
  > 상위 컴포넌트에서 사용한 이름을 그대로 하위 컴포넌트에서 사용해야 한다.

---------
## 예제
### Props 이용해서 하위 컴포넌트에 스타일 적용하기
```
<!DOCTYPE html>
<html lang="en">
    <body>
        <div id="root"></div>
    </body>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/prop-types@15.7.2/prop-types.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
        const root = document.getElementById("root");
        const Btn = ({ text, fontSize = 12 }) => {
            return (
                <button
                    style={{
                        backgroundColor: "tomato",
                        borderRadius: 10,
                        border: "1px solid tomato",
                        color: "white",
                        padding: "10px 5px",
                        fontSize,
                    }}
                >
                    {text}
                </button>
            );
        };
        Btn.propType = {
            text: PropTypes.string.isRequired,
            fontSize: PropTypes.number,
        };
        const App = () => {
            return (
                <div>
                    <Btn text="Save Changes" fontSize={18} />
                    <Btn text="Continue" />
                </div>
            );
        };
        ReactDOM.render(<App />, root);
    </script>
</html>

```


