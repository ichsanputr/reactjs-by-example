---
title: Props
layout: home
nav_order: 5
---
{: .fw-500 }
# Props

Props used for sending data from parent component into child component.

`ChildComponent.tsx`
```tsx
// use ? for optional prop so the parent componen can not to fill that prop
function ChildComponent(props: {
    name: string,
    description?: string,
    listName?: string[]
}) {
    return (
        <>
            <h1>Name: {props.name}</h1>
            <h1>Name: {props.description}</h1>
            <h1>Name: {props.listName}</h1>
        </>
    )
}

export default ChildComponent
```

`ParentComponent.tsx`
```tsx
import ParentComponent from "./ExampleComponent";

function App() {
  return (
    <>
      <ParentComponent name="Ichsan" />
    </>
  )
}

export default App
```