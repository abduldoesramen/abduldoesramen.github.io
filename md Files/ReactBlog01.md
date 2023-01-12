# 02/01/2023

### _<u>Before React</u>_:

Every web-page simply ran on:<br>

- Javascript, for interactivity
- HTML, to display text and simple elements.
- CSS, to stylise text and elements.

These were used to display and change the _DOM_.<br>
However, each browser (e.g Chrome, IE, Firefox…) had different ways to run Javascript.<br>
This problem was solved by _JQuery_, which used its own API to make sure Javascript code can run on every browser with no changes required.<br>

Though such applications became more and more complex: for example, FaceBook.<br>
We quickly changed to _Single-Page Applications_, where we now focus a lot more on the Javascript of an application - rather than refreshing/loading all the HTML/CSS/Javascript each time a user clicks on something.<br> Therefore the Javascript code itself is now in charge of updating the HTML/CSS.<br>

### _<u>React Concepts</u>_:<br>

<u>“Don’t touch the DOM, I’ll do it”</u><br>
_Imperative_: manipulating the DOM directly via DOM API (e.g library: element.innerHTML)<br>

- _Document Object Model_: The way a website displays things, manipulated by Javascript and is seen as a tree-representation of a page. <br>

_Declarative_: “DOM manipulation is a bottleneck: change/add elements, reflow: move and recalculate layout of page.”<br>

React instead only requires the blueprints (i.e. “state”) of how the page should look like - and automatically manipulates the DOM for us in the best way possible.<br>
To summarise: _[ Based on our state -> “React” and adjust/display our Page for us ]_<br>

<u>“Build websites like lego blocks”</u><br>
React is based on Reusable components (for example: Navbar) and has components within components.<br>
State: any data that describes our app (for example: isLoggedIn: True).<br>
Components are built based on that data simply as Javascript functions (receive Props, returns HTML inside JS).<br>

<u>“Unidirectional data flow”</u><br>
React is a JS library to increase interactivity in our apps.<br>
In React, we have state - which is an object that describes our app through data.<br>
We also have components that return HTML (JSX) inside our JS code.<br>
_JSX_: A HTML like syntax that is used inside Javascript code.<br>

A component and state with JSX is combined in React to create a VirtualDOM (tree like object).<br>
One way data flow is occurring because the VirtualDOM only changes when our state changes. Data can never move up on React. Such restriction can allow easier debugging of code (e.g. sign up button bugging - look at where data exists/flows through).<br>

<u>UI, The rest is up to you</u><br>
AngularJS was a framework (like a Kitchen: knife, pan, stove, etc.), very opinionated.<br>
React only works with the view (User Interface), anything else - use other modules yourself (like a Stove to cook on, your knife, spoon, etc. is your choice).<br>

- React Library: Components of a blueprint to make changes.<br>
- React DOM: Interacts with DOM and makes changes.<br>

React only needs the blueprint on how to change components. Therefore React can be used in any technology stack, for example: React Native.<br>

### _Important areas to focus on_:<br>

- Decide on Components
- Decide the State and where it lives
- What changes when state changes

<br>
<br>

# 02/01/2023

### _<u>Class Components</u>_:<br>

From what I have learnt, there are two main structures behind React, Class and Functional Components.<br>
The course I am currently undertaking has introduced classes first, as it is relatively more simple and allows for an easier understanding of Functional Components.<br>
Each class component always has a constructor and related methods associated with it. For example, React has in-built methods, such as Render and ComponentDidMount. The App component in particular, has a lifecycle associated with it and is as follows:<br>

- The App class initialises a default constructor that allows the user to setState by adding empty data structures and attributes.
- The App class then renders these empty data structures and attributes (hence why you momentarily see a blank page before additional renders).
- Finally, the App class then runs a method called "ComponentDidMount" and mounts any components the developer wishes to use.
- If any components update or use Set State or Props (that change the underlining address of attributes), React calls the render method again.<br>

Render always returns JSX, a HTML like syntax that has the ability to integrate Javascript via curly braces.

### _<u>Functional Components</u>_:<br>

Again, from my understanding Functional Components are similar yet different to Class Components.<br>
Functional Components take in arguments, that are the Props of this component, returns the same JSX we explored in Class Components; running top-to-bottom. <br>
Functional Components do not have any class, constructors or methods associated with them, nor do they any lifecycles we discussed about Class Components.<br>

In order to understand how Functional Components implement functionality similar to Render & ComponentDidMount - we need to understand Functions, Pure Functions, Inpure Functions and Side Effects.<br>

#### _<u>Pure and Inpure Functions</u>_:<br>

A <u>Pure Function</u> has two characteristics:

- It will always return the same result if given the same arguments, no matter how many time it is called.
- It has no side effects.
  - A <u>side effect</u> is when a function creates some kind of effect outside of its scope (e.g. setting a variable outside its scope).

The below code shows a pure function:

```
const pureFunc = (a, b) => {
    return a + b;
}
```

An <u>Inpure Function</u> also has two opposing characteristics:

- Has the capability to return different results despite despite giving
  the same arguments because it is based on external factors.
- Has side effects (pretty much modifies something outside of its scope).

In this example code, the function's output is dependent on an external factor, in this case it is the attribute "c".

```
>let c = 3
const inPureFunc = (a, b) => {
    return a + b + c;
}
>inPureFunc(1, 1)
5
>c = 1
>inPureFunc(1, 1)
3
```

Can you spot the side effect below?

```
>let c = 3
const inPureFunc = (a, b) => {
    c = a * b;
    return a + b
}
>inPureFunc(1, 2)
>console.log(c)
3
```
