# 1. Explain what is Long polling

As i have recently learned, Long polling is a method of achieving near real-time communication by repeatedly sending HTTP requests to a server, waiting for a response, and then sending another request. This is in contrast to short polling, which sends a request at a fixed interval regardless of whether a response has been received.

## a. provide a example implementation of long polling

A simple example of long polling in JavaScript:

```javascript
function longPoll() {
  fetch("/data")
    .then((response) => response.json())
    .then((data) => {
      // Handle new data
      longPoll();
    });
}
longPoll();
```

## b. what other alternatives are available instead of long polling explain at least one if any

An alternative to long polling is WebSockets, which allows for bi-directional communication between a client and a server in real-time.

## c. provide positive and negative impact of using long polling

The positive impact of using long polling is that it allows for near real-time communication without the need for a dedicated push service. The negative impact is that it can create a large number of open connections and may increase server load.

# 2. Explain the difference between cookies and local storage

Cookies and local storage are both ways to store data in a user's browser, but they have some key differences.

Cookies are small text files that are sent by the server and stored on the user's computer. They are typically used to track user preferences and login information. They have a size limit and are sent with every request to the server.

Local storage is a client-side storage mechanism that allows for storing key-value pairs in the browser. It has a larger storage limit than cookies and data is not sent to the server with every request. Local storage is accessible to JavaScript code running on the page, whereas cookies can also be read by the server.

# 3. How many HTTP methods are there? explain each of them.

- GET: retrieves information from the server
- POST: sends new information to the server
- PUT: updates existing information on the server
- DELETE: deletes information on the server
- PATCH: partially updates existing information on the server
- HEAD: retrieves the headers of a resource
- CONNECT: establishes a tunnel to the server for a different protocol
- OPTIONS: retrieves the options for a resource

# 4. Explain the difference between an object and an array

An object is a collection of key-value pairs, where the keys are unique strings and the values can be any data type. Objects are typically used to store data in a structured way, and properties can be accessed using dot notation or bracket notation. An array, on the other hand, is a linear collection of items, where each item can be of any data type and is identified by an index. Arrays are typically used to store lists of items, and items can be accessed using bracket notation.

# 5. What is react?

React is a JavaScript library for building user interfaces. It allows developers to build reusable components that can be easily composed to create complex UIs.

## a. what is react hooks used for?

React Hooks are functions that allow developers to use state and other React features in functional components. They were introduced as a way to improve code organization and avoid the need for class-based components.

## b. name 3 rules of hooks and why they exists

The three rules of Hooks are:

- Only call Hooks at the top level of your component or your own Hooks.
- Only call Hooks from React functions.
- The order of Hooks calls must be the same between renders.
- These rules exist to ensure that Hooks are called in a predictable order and to prevent bugs caused by state updates in unexpected places.

## c. what is jsx?

JSX is a syntax extension for JavaScript that allows developers to write HTML-like elements in their JavaScript code. It is used in React to define the structure of a component's UI.

## d. What are environment variables and how do you use them in react?

Environment variables are values that can be set in the environment in which a program runs. They can be used to configure the behavior of a program at runtime. In React, environment variables can be used to store sensitive information such as API keys and to configure the behavior of the app in different environments. They can be accessed through process.env object in Node.js. which is usually stored in a .env file.

## e. What are props?

Props are short for "properties" and are used to pass data from a parent component to a child component. They can be used to configure a component's behavior or to display dynamic data.

## f. how do you update state in react?

State in React can be updated using the setState() function, which takes an object that describes the changes to be made to the state. The component will re-render with the new state when setState() is called.

## g. can you return multiple element from a component?

Yes, you can return multiple elements from a component by wrapping them in a container element, such as a div.

## h. describe Component Driven Development and how it applies in react

Component-Driven Development (CDD) is a development approach in which the user interface is built by composing small, reusable components. This approach allows for a more modular, maintainable codebase and promotes the reuse of components across different parts of the application. React encourages this development approach by providing a way to build and compose components.

## i. Provide an example implementation of the following components:

### i. login Button:

```javascript
import React from "react";

function LoginButton() {
  const handleClick = () => {
    // Perform login logic
  };

  return <button onClick={handleClick}>Login</button>;
}

export default LoginButton;
```

### ii. a Group Component with the following values “React” ,“LIA” , “Carelyo“ each value can be selected:

```javascript
function GroupComponent() {
  const options = ["React", "LIA", "Carelyo"];
  const [selectedOption, setSelectedOption] = useState(options[0]);

  return (
    <div>
      {options.map((option) => (
        <button key={option} onClick={() => setSelectedOption(option)}>
          {option}
        </button>
      ))}
      <p>Selected option: {selectedOption}</p>
    </div>
  );
}

export default GroupComponent;
```

### iii. a Card Component with the following information (Name, Email, Image, Button):

```javascript
function CardComponent({ name, email, imageUrl, onButtonClick }) {
  return (
    <div>
      <img src={imageUrl} alt={name} />
      <p>Name: {name}</p>
      <p>Email: {email}</p>
      <button onClick={onButtonClick}>Button</button>
    </div>
  );
}

export default CardComponent;
```

### iv. an api call fetching information:

```javascript
import axios from "axios";

async function fetchData() {
  try {
    const response = await axios.get("https://example.com/api/data");
    return response.data;
  } catch (error) {
    console.error(error);
  }
}
```

### v. a custom hook of your choice:

```javascript
import { useState } from "react";

function useCounter() {
  const [count, setCount] = useState(0);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return { count, increment, decrement };
}

export default useCounter;
```

In the above example, the custom hook useCounter returns an object containing the current count, and functions to increment and decrement the count. The hook can be used in a component like this:

```javascript
import React, { useState } from "react";
import useCounter from "./useCounter";

function Counter() {
  const { count, increment, decrement } = useCounter();

  return (
    <div>
      <button onClick={decrement}>-</button>
      <span>{count}</span>
      <button onClick={increment}>+</button>
    </div>
  );
}
```

# 6. Complete the following challenges

## a. Challenge sequence 1

### challenge 1 of 3:

![Code snippet of challenge 1a](/assets/challenge-one.png)

### challenge 2 of 3:

![Code snippet of challenge 1b](/assets/challenge-two.png)

### challenge 3 of 3:

Solved with the help of provided solution.

## b. Challenge sequence 2

### challenge 1 of 4:

![Code snippet of challenge 2a](/assets/challenge-four.png)

### challenge 2 of 4:

![Code snippet of challenge 2b](/assets/challenge-five.png)

### challenge 3 of 4:

![Code snippet of challenge 2c](/assets/challenge-six.png)

### challenge 4 of 4:

![Code snippet of challenge 2d](/assets/challenge-seven.png)

## c. Challenge sequence 3

### challenge 1 of 2:

![Code snippet of challenge 3a](/assets/challenge-eight.png)

### challenge 2 of 2:

Solved with the help of provided solution.

# 7. What is typescript?

TypeScript is an open-source programming language that is a super set of JavaScript. It adds optional static typing, class-based object-oriented programming, and other features to JavaScript.

## a. what are the benefits of typescript?

- Improved code readability and maintainability by catching errors at compile-time
- Improved developer productivity by providing better tooling and editor support
- Improved code quality by enforcing a consistent code style
- Improved collaboration by making it easier to understand and work with code written by others

## b. provide positive and negative of typescript

Positive impacts:

- Improved code quality and maintainability
- Better tooling and editor support
- Easier collaboration

Negative impacts:

- Additional setup and configuration is required
- More time spent on type annotations
- Some developers may not be familiar with the syntax

## c. provide a code snippet in both javascript and typescript

Javascript:

```javascript
function add(a, b) {
  return a + b;
}
```

Typescript:

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

# 8. What is a user story?

A user story is a short, simple description of a feature or functionality that a user needs or wants. It is typically written from the user's perspective and used to capture the requirements of a project.

## a. write a simple example user story

A simple example user story: "As a user, I want to be able to find important content or search for products on the website header or navbar so that I can easily find what I'm looking for."

## b. use figma or excalidraw visualize it

![Image of figma sketch of a nav/ search bar](/assets/nav.png)

## c. how can user stories be used in development

User stories can be used in development as a way to guide the development process. They provide a clear understanding of what the end user needs or wants, which can be used to inform the design and development of the feature or functionality.

# 9. what is git?

Git is a distributed version control system (VCS) used for software development and other version control tasks. It allows developers to track changes made to the code, collaborate with others, and revert to previous versions of the code if necessary.

## a. what is git hooks

Git hooks are scripts that run automatically when certain Git events occur. They can be used to perform tasks such as validating code before it is committed, or automatically deploying code when it is pushed to a remote repository.

## b. what is conventional commit

Conventional commits is a specification for adding human-readable meaning to commit messages. It helps to generate more useful and structured commit history, making it easier to understand what changes were made and why.

## c. write a commit message for the following code change (created a new component and imported it into the the navbar component, the component shows up only when a user is logged and shows time left before the current session ends )

Commit message: "feat: created a new 'SessionExpiration' component and added it to the navbar, now displays remaining session time for logged-in users."

# 10. what is Accessibility on the web why is it important?

Accessibility on the web refers to the design and development of websites, applications, and tools to be inclusive of people with disabilities. This includes people with visual, auditory, motor, and cognitive disabilities.

## a. what are the benefit of building an accessible website

The benefits of building an accessible website include:

- Improved usability for people with disabilities
- Better search engine optimization
- Increased potential user base
- Legal compliance with accessibility laws

## b. name some pitfalls when creating website that affect accessibility

Some pitfalls when creating websites that affect accessibility include:

- Not providing alternative text for images
- Using color alone to convey information
- Not providing keyboard-only navigation
- Not providing sufficient contrast between text and background
- Using fixed-width design elements
- Not providing text alternatives for non-text content
- Not providing sufficient time for users to read and use content.

# 11. Name 5 things you do not know and want to learn.

- React framer motions

- React state management with Redux

- Advanced UX/UI design

- Web security

- Graphic design tools such as Adobe illustrator
