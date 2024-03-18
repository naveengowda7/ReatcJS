# Components

    Components are independent and reusable bits of codee. They serve the same purpose as JavaScript functions, but work in isolation and return HTML

    class-based-components

```
{
     function Component() {
         return(
             <div>Component</div>
         )
     }
 }
```

    &&

    function-based-componenets
    ```
    {
        class App extends Component{
             render(){
                return <h1>Hello horn</h1>
                }
        }
    }
    ```

# JSX

    JSX allows us to write HTML in REACT.
    KSX makes it easier to write and add HTML in REACT.

## Note :

    ```
     Whenever we need to return multiple elements,
     we have wrap it up in a single element
    ```
    ```
    The tags must be closed in this,
    Because the code will be compiled into pure **JavaScript
    ```
    ```
    here We have to use **className over class,
     because the keyword class has an other reserved meaning for it.
    ```
    ```
    here We have to use **htmlFor over for,
     because the keyword class has an other reserved meaning for it.
    ```

# Fragements:

    Where their is no use of sections,articles like
    Semantic tags, use these fragments their

# Expressions:

    With JSX you can write expressions inside curly
    braces. the expression can be a React variable,
    or property, or any other valid JavaScript expression
    JSX will execute the expression and return the result
    ```
    function App(){

const myName = "Naveen";
const multiply = (a,b) =>a\*b;
const specialClass = "simple-class";

return(
<>

<h1>{myName}</h1>
<p>2+2 = {2+2}</p>
<p>My Friends List:{["Sachi","Manvith"]}</p>
<p>4\*2 = {multiply(4,2)}</p>
<p className={specialClass}>This is a special class</p>
</>
)
}
```

# Lists:

    In React, you will render lists with some type
    of loop. The JavaScript map() array method is
    generally the preferred method.

    ** Note: Each ele in list should have a unique *key
    ```
    function App(){
        const numbers = [1,2,3,4,5];

        return(
            <>
            {numbers.map((number) => (<ul key={Math.random()}>
            <li>{number}</li></ul>))}
            </>
        )
    }
    ```

# Props:

    props are arguments passed into React components.
    Props are passed to components via HTML attributes.

# Conditional Rendering:

    Conditional Rendering in React works the sane way conditions
    work in JavaScript. Use JavaScript operators like if or the
    conditional operator to create elements representing
    the current state and let React update the UI to matcht them.
    c

```
   const ValidPassword = () => <h1>Valid Password</h1>
   const InvalidPassword = () => <h1>Invalid Passwod</h1>

   const Password = ({isValid}) =>{
       if(isValid){
           return <ValidPassword/>;

       }
       return <InvalidPassword/>;
   };

   function App(){
       return(
           <>
           <Password isValid={true}/>
           </>
       );
   }
```

# Styles:

    function Component(){
        return(
            <section>
                <h1 style={{color:"white,backgroundColor:"teal,padding:"2rem}}>Inline Style</h1>
            </section>
       );
    }

# React BootStrap:

    npm install react-bootstrap bootstrap
    import 'bootstrap/dist/css/bootstrap.min.css';

# Tailwind CSS:

    npx install -D tailwindcss
    npx tailwindcss init

    content:[
        "./src/**/*.{js,jsx,ts,tsx}",
    ],

    index.css ---> @tailwind base;
                   @tailwind components;
                   @tailwind utilities;
            import "./index.css"

# Icons:

    npm install react-icons --save

# Events:

    const handleClick = () =>{
        console.log("Clicked);
        alert("You click me!!);
    }

    const Button=()=>{
        return <button onClick={() => handleClick}>Click</button>
    }

# State:

    The state is a built-in React object that is used to contain data or
    information about the component. A component's state can change over time;
    Whenever it changes, the component re-renders

# Hoooks:

    They let you use state and other React features without writing a class.

# useState():

\*\* The react useState Hook allows us to track state in a function component.
State generally refers to data or properties that need to be tacking in
an application.

```
        import {useState} from "react";

        const Counter = () =>{
            const [Count,setCount] = useState(0);

            const increment = () =>{
                setCount(count+1);
            }

            const decrement = () =>{
                setCount(Count - 1);
            }

            return (
                <>
                    <h1>{Count}</h1>
                    <button onClick={increment}>+</button>
                    <button onClick={decrement}>-</button>
                </>
            );
        }
```

# useEffect():

\*\* The useEffect Hook allows you to perform side effects
in your componenets. Some examples of side effects are:
fetching data, directly updating the DOM

```
    function App() {

    const [value,setValue] = useState(0)

     // When component render for the first time, it will execute everything inside this
     // AnyTime we do (side effect)
     // Dependency List
        useEffect(() => {
            console.log("Hello")
            document.title = `Increment (${value})`
        })

        return (
            <>
                <h1>{value}</h1>
                <button onClick={() => setValue(value+1)}>Click Me</button>
            </>
        );
    }
```

# Prop Drilling:

\*\* A technique of passing a State data into Multiple Components.

```
                        A
                       / \
                      /   \
                  header  div
                  /         \
                 /           \
              li             ul

              to transfer the data from ul to li here,
              we have to 1st transfer it to <div>, then <A>,
              then <header> then alas finally to the <li>
```

## This Porblem Can be Solved By Context API

# Context API:

\*\* 1. Import (create context)

```
    import { createContext } from "react";
```

\*\* 2. Creating instance of (createConstext)

```
    export const Data = createContext();
```

\*\* 3. Wrap our component into Provider Component

```
    <Data.Provider value={name}>
        <ComponentC />
    </Data.Provider>
```

\*\* 4. Consume the data in the destination

```
    <Data.Consumer>
            {
                (name) =>{
                    return <h1>My nam is {name}</h1>
                }
            }
    </Data.Consumer>
```

# useContext():

    React Context is a way to manage state globally.
    It can be used together with the useState Hook
    to share state between deeply nested components
    more easily than with useState alone.

```
    const ComponentC = () =>{

    const name = useContext(Data);
    const age = useContext(Data2);

    return(
        <>
            <h1>
                my name is: {name}, I'm {age} years old
            </h1>
        </>
        )
    }
```

# useReducer():

    useReducer is a hook in React that is similar to useState,
    but it is designed for more complex state objects or state
    transitions that involve multiple subb-values. It allows
    you to manage state in a functional, immutable way.

1.  State
2.  Dispatch: [vale,setValue] --> change the data
3.  reducer : custom state logic
4.  Initial state : { object }

```
    function App() {

  const [state,dispatch] = useReducer(reducer,initialState)

  return (
    <>
    <h1>{state.count}</h1>
    <button onClick={() => dispatch({type:"increment"})}>+</button>
    <button onClick={() => dispatch({type:"decrement"})}>-</button>
    <button onClick={() => dispatch({type:"reset"})}>Reset</button>
    </>
  );
}

const initialState = {count:0};

const reducer =(state,action) =>{
  switch (action.type) {
    case "increment":
      return {
        ...state,
        count:state.count+1,
      }
      break;
    case "decrement":
      return {
        ...state,
        count:state.count-1,
      }
      break;
      case "reset":
        return {
          ...state,
          count:0,
        }


    default:
      return state;
      break;
  }
}
```

# useRef():
    useRef is ahook in React that allows you to access the 
    properties of a DOM element. It is useful when you
    need to access the value of an element, or the
    current dimensions of an element

```
    function App() {

  const inputElement = useRef(null)

  const focusInput = () =>{
     inputElement.current.focus()
     inputElement.current.value = "Naveen"
  }

  return (
  <>
  <input type="text" ref={inputElement}/>
    <button onClick={()=> focusInput()}>Focus & Write Naveen</button>
    </>
    );

}
```    
