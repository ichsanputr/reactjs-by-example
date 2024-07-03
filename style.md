---
title: Style
layout: home
nav_order: 3
---
{: .fw-500 }
# Style

Style can be done with `class` attribute, we can write all style directly or write on variable.

```tsx
import { useState } from "react";

function App() {
  const textStyle = {
    color: 'blue',
    fontSize: '20px',
    padding: '10px',
    borderRadius: '5px',
  };

  const [isActive, setIsActive] = useState(false)

  function toggleButton(){
    setIsActive((state) => state = !state)
  }

  return (
    <>
      <p style={ { fontSize: '20px', color: 'red' } }>
        Text with multiple properties without using variable
      </p>
      <p style={textStyle}>
        Text mith multiple properties
      </p>
      {/* multiple styling directly with ternary operator */}
      <button
        style={{
          backgroundColor: isActive ? 'green' : 'red',
          padding: '10px',
          borderRadius: '5px',
          cursor: 'pointer',
        }}
        onClick={toggleButton}
      >
        {isActive ? 'Active' : 'Inactive'}
      </button>
    </>
  )
}

export default App
```
