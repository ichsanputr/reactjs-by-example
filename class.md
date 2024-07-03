---
title: Class Styling
layout: home
nav_order: 2
---

{: .fw-500 }
# Class Styling

For use class we can write all class name in particular file and use the class name with `className` attribute, this acccept string for multiple class name directly or state variable.

To minimize and make the code still clean code we can use `classNames` package, this will be useful if you have multiple condition in your class list.

```tsx
import { useState } from "react"
import classNames from 'classnames';

function App() {
  const [textMain, setTextMain] = useState('text-red-500')

  function changeColorToBlue(){
    setTextMain((state) => state = 'text-blue-400')
  }

  const textClassNames = classNames('text-blue-900', {
    'text-4xl' : 2 == 2 ?? false
  });

  return (
    <>
      <p className={textMain}>
        Text main changed to blue when you click below button
      </p>
      <button onClick={changeColorToBlue}>Change Color to Blue</button>
      <p className="text-green-400 text-4xl">
        Text with multiple class directly
      </p>
      <p className={textClassNames}>
        Text with multiple class
      </p>
    </>
  )
}

export default App
```
