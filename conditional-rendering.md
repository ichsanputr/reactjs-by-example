---
title: Conditial Rendering
layout: home
nav_order: 5
---
{: .fw-500 }
# Conditional Rendering

Conditional rendering is how to determine rendering proccess an element based on particular condition. 

**Using if else return**, this not reccomended but it can to be use.
```tsx
function ExampleComponent(props: {
    name: string,
    show?: boolean
}) {
    if (props.show) {
        return (
            <><h1>Hello {props.name}</h1></>
        )
    } else {
        return (
            <><h1>Ups cannot displaying!</h1></>
        )
    }
}

export default ExampleComponent
```

**Ternary operator**, wrap conditional proccess with {} and return the element using ().
```tsx
function ExampleComponent(props: {
    name: string,
    show?: boolean
}) {

    return (
        <>
            {
                props.show ? (
                    <p>Hello {props.name}</p>
                ) : (
                    <p>Ups cannot display</p>
                )
            }
        </>
    )
}

export default ExampleComponent
```

**&& symbol**, wrap condition rendering with {} and follow the conditional using &&, if true element on right without wrap with () will be rendered.
```tsx
function ExampleComponent(props: {
    name: string,
    show?: boolean
}) {

    return (
        <>
            {
                props.show && <p>Hello {props.name}</p>
            }
        </>
    )
}

export default ExampleComponent
```

