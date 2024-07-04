---
title: useEffect
layout: home
nav_order: 7
---
{: .fw-500 }
# useEffect()

`useEffect()` will be running if any rendering happen, can caused by mounted application, state changed or props changed.

Does'nt passing the second parameter will be make run after when any rendering process happen.
```tsx
import { useState, useEffect } from "react";

function App() {
  const [number, setNumber] = useState(0)

  function incrNumber(){
    setNumber(state => state += 1)
  }

  useEffect(() => {
    console.log("Rendered something")
  })

  return (
    <>
      <p>{number}</p>
      <button onClick={incrNumber}>Increment Number</button>
    </>
  )
}

export default App
```
Passing the second parameter with particular props or state the callback only run after the given state/props changed or rerender.

```tsx
import { useState, useEffect } from "react";

function App() {
  const [number, setNumber] = useState(0)
  const [numberTwo, setNumberTwo] = useState(0)

  function incrNumber(){
    setNumber(state => state += 1)
  }

  function incrNumberTwo(){
    setNumberTwo(state => state += 1)
  }

  useEffect(() => {
    // only run if we Increment Number Second
    console.log("Rendered something")
  }, [numberTwo])

  return (
    <>
      <p>{number}</p>
      <p>{numberTwo}</p>
      <button onClick={incrNumber}>Increment Number</button>
      <button onClick={incrNumberTwo}>Increment Number Second</button>
    </>
  )
}

export default App
```

Pass empty array [] will be make only once after the component add to the DOM.
```tsx
import { useState, useEffect } from "react";

function App() {
  const [number, setNumber] = useState(0)

  function incrNumber(){
    setNumber(state => state += 1)
  }

  useEffect(() => {
    console.log("Component added to the DOM")
  }, [])

  return (
    <>
      <p>{number}</p>
      <button onClick={incrNumber}>Increment Number</button>
    </>
  )
}

export default App
```
