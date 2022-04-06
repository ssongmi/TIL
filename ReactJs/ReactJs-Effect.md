## Keyword
`ReactJs` `jsx`

## Reference
- [노마드 코더 ReactJS로 영화 웹 서비스 만들기](https://nomadcoders.co/react-for-beginners/lobby)

## 개념
#### React.useEffect(function, dependencyList)
  > dependencyList의 값들이 변할 때 마다 해야 할 동작들을 정의한다.
  > dependencyList가 비어있을 경우 렌더링 될 때 동작을 수행한다.
  > 화면의 렌더링이 완료된 후 실행된다.

#### clean-up 함수
  > React.useEffect에서 function의 반환값으로 clean-up 함수를 줄 수 있다.
  > 컴포넌트가 destroy될 때 실행된다

#### React.useMemo
  > 메모이제이션 된 값을 반환한다.
  > dependency가 변경되었을 때 메모이제이션 된 값만 다시 계산
  > 렌더링 중에 실행된다.

---------
## 예제
### React.useEffect
```
import Button from './Button';
import styles from "./App.module.css"
import { useEffect, useState } from "react";
import React from 'react';

const Hello = () => {
  useEffect(() => {
    console.log("created")
    return () => { console.log("destroyed") }
  }, []);
  return <h1>Hello</h1>
}
function App() {
  const [showing, setShowing] = useState(false);
  const onClick = () => {
    setShowing((cur) => !cur)
  }
  return <div>
    {showing ? <Hello /> : null}
    <button onClick={onClick}>{showing ? "hide" : "showing"}</button>
  </div>
}
export default App;

```

