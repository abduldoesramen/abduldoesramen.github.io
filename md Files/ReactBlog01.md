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

# 02/01/2023

### _<u>Class Components</u>_:

From what I have learnt, there are two main structures behind React, Class and Functional Components.<br>
The course I am currently undertaking has introduced classes first, as it is relatively more simple and allows for an easier understanding of Functional Components.<br>
Each class component always has a constructor and related methods associated with it. For example, React has in-built methods, such as Render and ComponentDidMount. The App component in particular, has a lifecycle associated with it.
