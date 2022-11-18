## What is React JS?
React js is a javascript library for building user interfaces. It is maintained by Facebook and a community of individual developers and companies. React can be used as a base in the development of single-page or mobile applications.

Competitors of React js
- Angular
- Vue

## What is a single-page application?
A single-page application is a web application or website that interacts with the browser by dynamically rewriting the current web page with new data from the web server, instead of the default method of the browser loading entire new pages. The page does not reload at any point in the process, nor does control transfer to another page, although the location hash or the HTML5 History API can be used to provide the perception and navigability of separate logical pages in the application.

## what is virtual DOM?
The virtual DOM (VDOM) is an in-memory representation of the Real DOM. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing's power to directly change what's on the screen. Virtual DOM is faster than the real DOM because it's a lightweight copy.

React JS is a component-based library. It means that we can divide our user interface into small independent and reusable pieces called components. We can use these components to build complex user interfaces.

There are two types of components in React js:

- Class components
- Functional components

## Class components
Class components are also called as stateful components. These components are defined using ES6 classes. These components have their own state and lifecycle methods. We can use these components when we need to use state and lifecycle methods.

Example of class component:

    class App extends React.Component {
        render() {
            return (
                <div>
                    <h1>Hello World</h1>
                </div>
            );
        }
    }

## Functional components
Functional components are also called as stateless components. These components are defined using functions. These components do not have their own state and lifecycle methods. We can use these components when we do not need to use state and lifecycle methods.

Example of functional component:

    function App() {
        return (
            <div>
                <h1>Hello World</h1>
            </div>
        );
    }

## What is state?
State is a plain javascript object that is used to store the component data. State is private and fully controlled by the component.

## what is lifecycle methods?
Lifecycle methods are methods that are called at various stages of the component life cycle. These methods are called in a specific order during the life cycle of a component.

## Difference between stateful and stateless components

| Stateful components | Stateless components |
|---------------------|----------------------|
| Class components | Functional components |
| Have their own state | Do not have their own state |
| Have their own lifecycle methods | Do not have their own lifecycle methods |
| Can use state and lifecycle methods | Can not use state and lifecycle methods |

## importing react

    import React from 'react';

In newer versions of React, we can skip the above code.

## What is JSX?
JSX is a syntax extension to JavaScript. It is used with React to describe what the UI should look like. JSX may remind you of a template language, but it comes with the full power of JavaScript.

Example of JSX:

    const element = <h1>Hello, world!</h1>;

Its similar to HTML but it is not HTML. JSX produces React "elements".

## Installing React JS

    npx create-react-app app-name
    cd app-name
    // to start the app
    npm start

## React folder structure
- public
- src
- package.json
- package-lock.json
- README.md
- node_modules

## public folder
This folder contains the index.html file. This is the main html file of the application. This file is the entry point of the application.

## src folder
This folder contains all the react components. This folder contains the index.js file. This is the main javascript file of the application. This file is the entry point of the application.

## package.json
This file contains the information about the project. This file contains the information about the dependencies of the project.

## package-lock.json
This file contains the information about the dependencies of the project.

## README.md
This file contains the information about the project and how to run the project. Its like a documentation of the project.

## node_modules
This folder contains all the dependencies of the project.

## What is ReactDOM?
ReactDOM is the package that is used to render the react components to the DOM. ReactDOM is the glue between react and the DOM.

## Diffience between JSX and HTML
| JSX | HTML |
|-----|------|
| JSX tags can use JavaScript expressions inside curly braces. | HTML tags can not use JavaScript expressions inside curly braces. |
| JSX have classnames instead of class. | HTML have class instead of classnames. |

## Writing component using arrow function
    const App = () => {
        return (
            <div>
                <h1>Hello World</h1>
            </div>
        );
    }

## ternary operator
    const App = () => {
        const name = "sandy";
        const isNameShowing = true;
        return (
            <div>
                <h1>Hello {isNameShowing ? name: "world"}</h1>
            </div>
        );
    }

## creating a custom component and calling the component

    const Name = () => {
        return (
            <div>
                <h1>Sandy</h1>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Name />
            </div>
        );
    }

When component is called, it is called as a tag. It is called as a self closing tag.

The advantage of using custom components is that we can reuse the components.

Example of having custom components:

    const Name = () => {
        return (
            <div>
                <h1>Sandy</h1>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Name />
                <Name />
                <Name />
            </div>
        );
    }

### But what is the use of having multiple components with the same name? 

For that we can pass props to the component.

## What is props?
Props is used to pass data from one component to another component. Props are immutable. Props are passed to the component as attributes.
Dynamic data is passed to the component using props.

Example of passing props to the component:

    const Name = (props) => {
        return (
            <div>
                <h1>{props.name}</h1>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Name name="sandy" />
                <Name name="sandeep" />
                <Name name="sandhya" />
            </div>
        );
    }

### Another way of passing props to the component
    const Name = ({ name }) => {
        return (
            <div>
                <h1>{name}</h1>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Name name="sandy" />
                <Name name="sandeep" />
                <Name name="sandhya" />
            </div>
        );
    }

For string props, we can use single or double quotes. For dynamic props, we can use curly braces.

### Having multiple props
    const Name = ({ name, age }) => {
        return (
            <div>
                <h1>{name}</h1>
                <h1>{age}</h1>
            </div>
        );
    }

    const App = () => {
        return (
            <div>
                <Name name="sandy" age="25" />
                <Name name="sandeep" age="26" />
                <Name name="sandhya" age="27" />
            </div>
        );
    }

### Having dynamic props
    const Name = ({ name, age }) => {
        return (
            <div>
                <h1>{name}</h1>
                <h1>{age}</h1>
            </div>
        );
    }

    const App = () => {
        const names = [
            { name: "sandy", age: 25 },
            { name: "sandeep", age: 26 },
            { name: "sandhya", age: 27 }
        ];
        return (
            <div>
                {names.map((name) => (
                    <Name name={name.name} age={name.age} />
                ))}
            </div>
        );
    }

## What are react hooks?
React hooks are functions that let you “hook into” React state and lifecycle features from function components. React hooks are used to add state and lifecycle methods to functional components.

## Types of react hooks
| Hook | Description |
|------|-------------|
| useState | useState is a hook that is used to add state to functional components. |
| useEffect | useEffect is a hook that is used to add lifecycle methods to functional components. |
| useContext | useContext is a hook that is used to add context to functional components. |

## useState hook
example of useState hook:

    import React, { useState } from "react";

    const App = () => {
        const [name, setName] = useState("sandy");
        return (
            <div>
                <h1>{name}</h1>
                <button onClick={() => setName("sandeep")}>Change Name</button>
            </div>
        );
    }

### What is events in react?
Events are actions or occurrences that happen in the system you are programming, which the system tells you about so you can respond to them in some way if desired. When you write programs, you often need to respond to events that happen in the browser. For example, when a user clicks a button, you want to respond to that click.

### What is event handler?
An event handler is a function that is called when an event occurs. For example, when a user clicks a button, you want to execute some code.

### code for counter
    import React, { useState } from "react";

    const App = () => {
        const [count, setCount] = useState(0);
        return (
            <div>
                <h1>{count}</h1>
                <button onClick={() => setCount((prevCount) => prevCount + 1)}>
                    Increment
                </button>
                <button onClick={() => setCount((prevCount) => prevCount - 1)}>
                    Decrement
                </button>
            </div>
        );
    }

**Code explanation**

    const [count, setCount] = useState(0);

Here, count is the state variable and setCount is the function to update the state variable.

    <h1>{count}</h1>

Here, count is the state variable.

    <button onClick={() => setCount((prevCount) => prevCount + 1)}>
        Increment
    <button onClick={() => setCount((prevCount) => prevCount - 1)}>
        Decrement

Here, setCount is the function to update the state variable.

prevCount is used to get the previous value of the state variable.

## useEffect hook
example of useEffect hook:

    import React, { useState, useEffect } from "react";

    const App = () => {
        const [count, setCount] = useState(0);
        useEffect(() => {
            console.log("useEffect called");
        });
        return (
            <div>
                <h1>{count}</h1>
                <button onClick={() => setCount((prevCount) => prevCount + 1)}>
                    Increment
                </button>
                <button onClick={() => setCount((prevCount) => prevCount - 1)}>
                    Decrement
                </button>
            </div>
        );
    }

**Code explanation**
    
        useEffect(() => {
            console.log("useEffect called");
        });
useEffect is called after every render.

## useEffect with dependency array

    import React, { useState, useEffect } from "react";

    const App = () => {
        const [count, setCount] = useState(0);
        useEffect(() => {
            console.log("useEffect called");
        }, [count]);
        return (
            <div>
                <h1>{count}</h1>
                <button onClick={() => setCount((prevCount) => prevCount + 1)}>
                    Increment
                </button>
                <button onClick={() => setCount((prevCount) => prevCount - 1)}>
                    Decrement
                </button>
            </div>
        );
    }

**Code explanation**
useEffect is called only when count is changed. If we remove the dependency array, useEffect is called after every render.

### use of dependency array
The dependency array is used to specify the values on which the useEffect hook depends. If the value of the dependency array is changed, useEffect is called. If the value of the dependency array is not changed, useEffect is not called.

## what is callback function?
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

example of callback function:

    function greeting(name) {
        alert("Hello " + name);
    }

    function processUserInput(callback) {
        var name = prompt("Please enter your name.");
        callback(name);
    }

    processUserInput(greeting);

Code explanation:

    function greeting(name) {
        alert("Hello " + name);
    }

Here, greeting is the function.

    function processUserInput(callback) {
        var name = prompt("Please enter your name.");
        callback(name);
    }

Here, processUserInput is the outer function and callback is the argument.

    processUserInput(greeting);

Here, greeting is the callback function.

***Note*: Never modify the state variable manually. Always use the function to update the state variable.**

## Map function in react

    import React from "react";

    const App = () => {
        const names = ["sandy", "sandeep", "sandhya"];
        return (
            <div>
                {names.map((name) => (
                    <h1>{name}</h1>
                ))}
            </div>
        );
    }

**Code explanation**
    
        {names.map((name) => (
            <h1>{name}</h1>
        ))}

Here, names is the array and map is the function to iterate the array.


# Building React Movie Search Application
### Topics covered
- React
- React hooks
    * useState
    * useEffect
- Calling External API

#### Basic Calling API in React using useEffect

    import React, {useEffect} from 'react';

    const API_URL = 'http://www.omdbapi.com/?apikey=YOUR_API'

    const App = () => {

        const searchMovies = async (title) => {
            const response = await fetch(API_URL + '&s=' + title)
            const data = await response.json()
            console.log(data)
        }

        useEffect(() => {
            searchMovies('avengers')
        }, [])

        return (
            <div>
                <h1>Movie Search</h1>
            </div>
        )
    }

    export default App

**Code explanation**

    const searchMovies = async (title) => {
        const response = await fetch(API_URL + '&s=' + title)
        const data = await response.json()
        console.log(data)
    }

Here, searchMovies is the function to call the API.
searchMovies is a callback function.
async is used to call the API asynchronously.
await is used to wait for the response from the API.
fetch is used to call the API.
response.json() is used to convert the response to json format.

    useEffect(() => {
        searchMovies('avengers')
    }, [])

Here, useEffect is used to call the API after every render.

#### code inside App function (static code)

    return (
        <div className="app">
            <h1>Movie Search</h1>
            <div className="search">
                <input 
                    placeholder="Search Movies"
                    value = "avengers"
                    onChange = {() => {}}
                 />
                <img 
                    src={SearchIcon}} 
                    alt="search" 
                    onClick={() => {}}
                />
            </div>
            <div className = "container">
                <div className = "movie">
                    <div>
                        <p>Movie Name</p>
                    </div>
                    <div>
                        <img src="MoviePoster" alt="movie poster" />
                </div>
                <div>
                    <span>Movie Type</span>
                    <h3>Movie Title</h3>
                </div>
            </div>
        </div>
    )

**Code explanation**
    
        <div className="search">
            <input 
                placeholder="Search Movies"
                value = "avengers"
                onChange = {() => {}}
            />
            <img 
                src={SearchIcon}} 
                alt="search" 
                onClick={() => {}}
            />
        </div>

Here, search is the div to search the movie.
input is used to enter the movie name.
onChange is used to call the searchMovies function when the input value is changed and its empty now.
img is used to display the search icon.
onClick is used to call the searchMovies function when the search icon is clicked and its empty now.

    <div className = "container">
        <div className = "movie">
            <div>
                <p>Movie Name</p>
            </div>
            <div>
                <img src="MoviePoster" alt="movie poster" />
            </div>
            <div>
                <span>Movie Type</span>
                <h3>Movie Title</h3>
            </div>
        </div>
    </div>

Here, container is the div to display the movie details.

Here whole code is static. We need to make it dynamic.

So custom components are needed to make the code dynamic.

#### Creating custom components

**MovieName.jsx**

Note: MovieName.jsx is the custom component.
Note: function name can be anything. Its not necessary to be same as the file name. But it is recommended to be same as the file name for good coding practices.

    import React from 'react'

    const MovieCard = ({movie1}) => {
        return (
            <div className = "movie">
                <div>
                    <p>{movie1.Year}</p>
                </div>
                <div>
                    <img src={movie1.Poster !== 'N/A' ? movie1.Poster : 'https://via.placeholder.com/300x450'} alt="movie poster" />
                </div>
                <div>
                    <span>{movie1.Type}</span>
                    <h3>{movie1.Title}</h3>
                </div>
            </div>
        )
    }

    export default MovieCard

**Code explanation**
    
        <div className = "movie">
            <div>
                <p>{movie1.Year}</p>
            </div>
            <div>
                <img src={movie1.Poster} alt="movie poster" />
            </div>
            <div>
                <span>{movie1.Type}</span>
                <h3>{movie1.Title}</h3>
            </div>
        </div>

Here, movie is the div to display the movie details.
movie1 is the object to store the movie details.
movie1 is passed as a prop to the MovieCard component. Object destructuring is used to access the movie1 object instead of using props.movie1.
movie1.Year is the year of the movie.
movie1.Poster is the poster of the movie.
The poster is not available for all the movies. So, we need to check whether the poster is available or not. If the poster is not available, then we need to display the placeholder image.
movie1.Type is the type of the movie.
movie1.Title is the title of the movie.

**App.js**

    import React, {useEffect} from 'react';
    import MovieCard from './MovieCard';

    const movie1 = {
        Title: 'Avengers',
        Year: '2012',
        Poster: 'N/A',
        Type: 'Action'
    }

    const App = () => {
            
        const searchMovies = async (title) => {
            const response = await fetch(API_URL + '&s=' + title)
            const data = await response.json()
            console.log(data)
        }
    
        useEffect(() => {
            searchMovies('avengers')
        }, [])
    
        return (
            <div className="app">
                <h1>Movie Search</h1>
                <div className="search">
                    <input 
                        placeholder="Search Movies"
                        value = "avengers"
                        onChange = {() => {}}
                    />
                    <img 
                        src={SearchIcon}} 
                        alt="search" 
                        onClick={() => {}}
                    />
                </div>
                <div className = "container">
                    <MovieCard movie1={movie1} />
                </div>
            </div>
        )
    }

    export default App

**Code explanation**

    const movie1 = {
        Title: 'Avengers',
        Year: '2012',
        Poster: 'N/A',
        Type: 'Action'
    }

Here, movie1 is the object to store the movie details.

    <MovieCard movie1={movie1} />

Here, movie1 is passed as a prop to the MovieCard component.

