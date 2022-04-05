## Keyword
`ReactJs` `jsx`

## Reference
- [노마드 코더 ReactJS로 영화 웹 서비스 만들기](https://nomadcoders.co/react-for-beginners/lobby)

## 개념
#### npx create-react-app project_name
  > 리액트 프로젝트 생성

#### *.module.css
  > js에서 import를 통해 스타일을 불러와 className으로 적용가능

---------
## 예제
### App.js
```
import Button from './Button';
import styles from "./App.module.css"
function App() {
  return (
    <div className="App">
      <p className={styles.title}>Hello</p>
      <Button text="continue" />
    </div>
  );
}

export default App;
```

### App.module.css
```
.title {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size:18px;
    font-weight:bold;
}
```

