## Keyword
`ReactJs` `state`

## Reference
- [노마드 코더 ReactJS로 영화 웹 서비스 만들기](https://nomadcoders.co/react-for-beginners/lobby)
- [React 공식문서](https://ko.reactjs.org/docs/faq-state.html)

## 개념
#### State
  > 렌더링 결과물에 영향을 주는 정보를 가지고 있는 일반 JavaScript 객체이다.   
  > 함수 내에 선언된 변수처럼 컴포넌트 안에서 관리된다.   
  > state가 바뀌면 컴포넌트가 리렌더링 된다.

#### React.useState()
  > 매개변수로 state의 default 값을 줄 수 있다.   
  > 반환값은 [variable, setVariable]로 변수와 modifier 함수이다.

---------
## 예제
### convert 프로그램 만들기
  > select 값에 따라 알맞은 변환기 셋팅  
  > 시간 → 분 & 분 → 시간으로 변환  
  > Km → Mile & Mile → Km으로 변환

```
<!DOCTYPE html>
<html lang="en">
    <body>
        <div id="root"></div>
    </body>
    <script src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script type="text/babel">
        const root = document.getElementById("root");
        const MinutesToHours = () => {
            const [amount, setAmount] = React.useState(0);
            const [inverted, setInverted] = React.useState(false);
            const onChange = (event) => {
                setAmount(event.target.value);
            };
            const onInvert = () => {
                reset();
                setInverted((current) => !current);
            };
            const reset = () => setAmount(0);
            return (
                <div>
                    <div>
                        <label htmlFor="minutes">Minutes</label>
                        <input
                            type="number"
                            id="minutes"
                            value={inverted ? amount * 60 : amount}
                            placeholder="minutes"
                            onChange={onChange}
                            disabled={inverted}
                        ></input>
                    </div>
                    <div>
                        <label htmlFor="hours">Hours</label>
                        <input
                            type="number"
                            id="hours"
                            placeholder="Hours"
                            value={inverted ? amount : Math.round(amount / 60)}
                            disabled={!inverted}
                            onChange={onChange}
                        ></input>
                    </div>
                    <button onClick={reset}>reset</button>
                    <button onClick={onInvert}>{inverted ? "Tunr back" : "Invert"}</button>
                </div>
            );
        };
        const KmToMiles = () => {
            const [amount, setAmount] = React.useState(0);
            const [inverted, setInverted] = React.useState(false);
            const onChange = (event) => {
                setAmount(event.target.value);
            };
            const onReset = () => {
                setAmount(0);
            };
            const onInvert = () => {
                onReset();
                setInverted((current) => !current);
            };
            return (
                <div>
                    <div>
                        <label htmlFor="km">Km</label>
                        <input
                            id="km"
                            type="number"
                            disabled={inverted}
                            value={inverted ? amount / 0.62137 : amount}
                            onChange={onChange}
                        />
                    </div>
                    <div>
                        <label htmlFor="mile">Mile</label>
                        <input
                            id="mile"
                            type="number"
                            disabled={!inverted}
                            value={inverted ? amount : amount * 0.62137}
                            onChange={onChange}
                        />
                    </div>
                    <button id="reset" onClick={onReset}>
                        reset
                    </button>
                    <button id="invert" onClick={onInvert}>
                        {inverted ? "Turn back" : "Invert"}
                    </button>
                </div>
            );
        };
        const App = () => {
            const [index, setIndex] = React.useState("xx");
            const onSelect = (event) => {
                setIndex(event.target.value);
            };
            return (
                <div>
                    <h1>Super Converter</h1>
                    <select value={index} onChange={onSelect}>
                        <option value="xx">Please select your units</option>
                        <option value="0">Minutes & Hours</option>
                        <option value="1">Km & Miles</option>
                    </select>
                    <hr />
                    {index == "xx" ? "Please select your units" : null}
                    {index == "0" ? <MinutesToHours /> : null}
                    {index == "1" ? <KmToMiles /> : null}
                </div>
            );
        };
        ReactDOM.render(<App />, root);
    </script>
</html>
```
