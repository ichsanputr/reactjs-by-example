---
title: useMemo
layout: home
nav_order: 4
---
{: .fw-500 }
# Style

`useMemo()` will be rerunning if any changes happen on state which we pass in depedency array on second parameter.

```tsx
import { useMemo, useState } from "react";

function App() {
  const [square, setSquare] = useState(0)

  // second parameter is dependency which will recompute when the state changed
  const squareCalc = useMemo(() => {
    return square * square
  }, [square])

  function onChangelength(event: any){
    // change square state when input value changed
    setSquare((state) => state = event.target.value)
  }

  return (
    <>
      {/* display squareCalc which from square * square */}
      <p style={{ fontSize: '20px', color: 'red' }}>
        {squareCalc}
      </p>
      <input type="number" onChange={onChangelength}/>
    </>
  )
}

export default App

```
