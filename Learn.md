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
    The react useState Hook allows us to track state in a function component.
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
