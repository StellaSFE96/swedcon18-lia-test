# 1. Explain what is Long polling

Long polling is a method of achieving near real-time communication by repeatedly sending HTTP requests to a server, waiting for a response, and then sending another request. This is in contrast to short polling, which sends a request at a fixed interval regardless of whether a response has been received.

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

Local storage, on the other hand, is a client-side storage mechanism that allows for storing key-value pairs in the browser. It has a larger storage limit than cookies and data is not sent to the server with every request. Local storage is accessible to JavaScript code running on the page, whereas cookies can also be read by the server.

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

## i. provide an example implementation of the following components:

### i.Login Button

### ii. A Group Component with the following values “React” ,“LIA” , “Carelyo“ each value can be selected

### iii. A Card Component with the following information (Name, Email, Image, Button)

### iv. An api call fetching information

### v. a custom hook of your choice

# 6. complete the following challenges

## a. Challenge 1

## b. Challenge 2

## c. Challenge 3

# 7. What is typescript?

## a. what are the benefits of typescript?

## b. provide positive and negative of typescript

## c. provide a code snippet in both javascript and typescript

# 8. What is a user story?

## a. write a simple example user story

## b. use figma or excalidraw visualize it

## c. how can user stories be used in development

# 9. what is git?

## a. what is git hooks

## b. what is conventional commit

## c. write a commit message for the following code change (created a new component and imported it into the the navbar component, the component shows up only when a user is logged and shows time left before the current session ends )

# 10. what is Accessibility on the web why is it important?

## a. what are the benefit of building an accessible website

## b. name some pitfalls when creating website that affect accessibility

# 11. Name 5 things you do not know and what to learn.
