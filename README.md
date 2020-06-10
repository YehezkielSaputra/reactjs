## React JS

## Table of Contents

### React Basics

| No. |  Questions                                   |
|-----|----------------------------------------------|
| 01. | [What is React?](#what-is-react) |
| 02. | [What are the major features of React?](#what-are-the-major-features-of-react) |
| 03. | [What is JSX?](#what-is-jsx) |
| 04. | [What is the difference between Element and Component?](#what-is-the-difference-between-element-and-component) |
| 05. | [How to create components in React?](#how-to-create-components-in-react) |
| 06. | [When to use a Class Component over a Function Component?](#when-to-use-a-class-component-over-a-function-component) |
| 07. | [What are Pure Components?](#what-are-pure-components) |
| 08. | [What is state in React?](#what-is-state-in-react) |
| 09. | [What are props in React?](#what-are-props-in-react) |
| 10. | [What is the difference between state and props?](#what-is-the-difference-between-state-and-props) |
| 11. | [Why should we not update the state directly?](#why-should-we-not-update-the-state-directly) |
| 12. | [What is the purpose of callback function as an argument of setState()?](#what-is-the-purpose-of-callback-function-as-an-argument-of-setstate)
| 13. | [What is the difference between HTML and React event handling?](#what-is-the-difference-between-html-and-react-event-handling) |
| 14. | [How to bind methods or event handlers in JSX callbacks?](#how-to-bind-methods-or-event-handlers-in-jsx-callbacks) |
| 15. | [How to pass a parameter to an event handler or callback?](#how-to-pass-a-parameter-to-an-event-handler-or-callback) |
| 16. | [What are synthetic events in React?](#what-are-synthetic-events-in-react) |
| 17. | [What is inline conditional expressions?](#what-is-inline-conditional-expressions) |
| 18. | [What are "key" props and what is the benefit of using them in arrays of elements?](#what-are-key-props-and-what-is-the-benefit-of-using-them-in-arrays-of-elements) |
| 19. | [What is the use of refs?](#what-is-the-use-of-refs) |
| 20. | [How to create refs?](#how-to-create-refs) |
| 21. | [What are forward refs?](#what-are-forward-refs) |
| 22. | [Which is preferred option with in callback refs and findDOMNode()?](#which-is-preferred-option-with-in-callback-refs-and-finddomnode) |
| 23. | [Why are String Refs legacy?](#why-are-string-refs-legacy) |
| 24. | [What is Virtual DOM?](#what-is-virtual-dom) |
| 25. | [How Virtual DOM works?](#how-virtual-dom-works) |
| 26. | [What is the difference between Shadow DOM and Virtual DOM?](#what-is-the-difference-between-shadow-dom-and-virtual-dom) |
| 27. | [What is React Fiber?](#what-is-react-fiber) |
| 28. | [What is the main goal of React Fiber?](#what-is-the-main-goal-of-react-fiber) |
| 29. | [What are controlled components?](#what-are-controlled-components) |
| 30. | [What are uncontrolled components?](#what-are-uncontrolled-components) |
| 31. | [What is the difference between createElement and cloneElement?](#what-is-the-difference-between-createelement-and-cloneelement) |
| 32. | [What is Lifting State Up in React?](#what-is-lifting-state-up-in-react) |
| 33. | [What are the different phases of component lifecycle?](#what-are-the-different-phases-of-component-lifecycle) |
| 34. | [What are the lifecycle methods of React?](#what-are-the-lifecycle-methods-of-react) |
| 35. | [What are Higher-Order components?](#what-are-higher-order-components) |
| 36. | [How to create props proxy for HOC component?](#how-to-create-props-proxy-for-hoc-component) |
| 37. | [What is context?](#what-is-context) |
| 38. | [What is children prop?](#what-is-children-prop) |
| 39. | [How to write comments in React?](#how-to-write-comments-in-react) |
| 40. | [What is the purpose of using super constructor with props argument?](#what-is-the-purpose-of-using-super-constructor-with-props-argument) |

## React Basics

01. ### What is React?
    React is an **open-source frontend JavaScript library** which is used for building user interfaces especially for single page applications. It is used for handling view layer for web and mobile apps. React was created by [Jordan Walke](https://github.com/jordwalke), a software engineer working for Facebook. React was first deployed on Facebook's News Feed in 2011 and on Instagram in 2012.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

02. ### What are the major features of React?
    The major features of React are:
    * It uses **VirtualDOM** instead RealDOM considering that RealDOM manipulations are expensive.
    * Supports **server-side rendering**.
    * Follows **Unidirectional** data flow or data binding.
    * Uses **reusable/composable** UI components to develop the view.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

03. ### What is JSX?
    *JSX* is a XML-like syntax extension to ECMAScript (the acronym stands for *JavaScript XML*). Basically it just provides syntactic sugar for the `React.createElement()` function, giving us expressiveness of JavaScript along with HTML like template syntax.

    In the example below text inside `<h1>` tag return as JavaScript function to the render function.

    ```jsx harmony
    class App extends React.Component {
      render() {
        return(
          <div>
            <h1>{'Welcome to React world!'}</h1>
          </div>
        )
      }
    }
    ```
    
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

04. ### What is the difference between Element and Component?
    An *Element* is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components. *Elements* can contain other *Elements* in their props. Creating a React element is cheap. Once an element is created, it is never mutated.

    The object representation of React Element would be as follows:

    ```javascript
    const element = React.createElement(
      'div',
      {id: 'login-btn'},
      'Login'
    )
    ```

    The above `React.createElement()` function returns an object:

    ```
    {
      type: 'div',
      props: {
        children: 'Login',
        id: 'login-btn'
      }
    }
    ```

    And finally it renders to the DOM using `ReactDOM.render()`:

    ```html
    <div id='login-btn'>Login</div>
    ```

    Whereas a **component** can be declared in several different ways. It can be a class with a `render()` method. Alternatively, in simple cases, it can be defined as a function. In either case, it takes props as an input, and returns a JSX tree as the output:

    ```javascript
    const Button = ({ onLogin }) =>
      <div id={'login-btn'} onClick={onLogin}>Login</div>
    ```

    Then JSX gets transpiled to a `React.createElement()` function tree:

    ```javascript
    const Button = ({ onLogin }) => React.createElement(
      'div',
      { id: 'login-btn', onClick: onLogin },
      'Login'
    )
    ```
   
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

05. ### How to create components in React?
    There are two possible ways to create a component.
    1. **Function Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as first parameter and return React elements:

        ```jsx harmony
        function Greeting({ message }) {
          return <h1>{`Hello, ${message}`}</h1>

        }
        ```

    2. **Class Components:** You can also use ES6 class to define a component. The above function component can be written as:

        ```jsx harmony
        class Greeting extends React.Component {
          render() {
            return <h1>{`Hello, ${this.props.message}`}</h1>
          }
        }
        ```
        
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

06. ### When to use a Class Component over a Function Component?
    If the component needs *state or lifecycle methods* then use class component otherwise use function component.
    *However, from React 16.8 with the addition of Hooks, you could use state , lifecycle  methods and other features that were only available in class component right in your function component.*

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

07. ### What are Pure Components?
    *`React.PureComponent`* is exactly the same as *`React.Component`* except that it handles the `shouldComponentUpdate()` method for you. When props or state changes, *PureComponent* will do a shallow comparison on both props and state. *Component* on the other hand won't compare current props and state to next out of the box. Thus, the component will re-render by default whenever `shouldComponentUpdate` is called.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

08. ### What is state in React?
    *State* of a component is an object that holds some information that may change over the lifetime of the component. We should always try to make our state as simple as possible and minimize the number of stateful components. Let's create an user component with message state,

    ```jsx harmony
    class User extends React.Component {
      constructor(props) {
        super(props)

        this.state = {
          message: 'Welcome to React world'
        }
      }

      render() {
        return (
          <div>
            <h1>{this.state.message}</h1>
          </div>
        )
      }
    }
    ```

    ![state](assets/state.jpg)

    State is similar to props, but it is private and fully controlled by the component. i.e, It is not accessible to any component other than the one that owns and sets it.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

09. ### What are props in React?
    *Props* are inputs to components. They are single values or objects containing a set of values that are passed to components on creation using a naming convention similar to HTML-tag attributes. They are data passed down from a parent component to a child component.

    The primary purpose of props in React is to provide following component functionality:
    1. Pass custom data to your component.
    2. Trigger state changes.
    3. Use via `this.props.reactProp` inside component's `render()` method.

    For example, let us create an element with `reactProp` property:

    ```jsx harmony
    <Element reactProp={'1'} />
    ```

    This `reactProp` (or whatever you came up with) name then becomes a property attached to React's native props object which originally already exists on all components created using React library.

    ```
    props.reactProp
    ```
    
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

10. ### What is the difference between state and props?
    Both *props* and *state* are plain JavaScript objects. While both of them hold information that influences the output of render, they are different in their functionality with respect to component. Props get passed to the component similar to function parameters whereas state is managed within the component similar to variables declared within a function.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

11. ### Why should we not update the state directly?
    If you try to update state directly then it won't re-render the component.

    ```javascript
    //Wrong
    this.state.message = 'Hello world'
    ```

    Instead use `setState()` method. It schedules an update to a component's state object. When state changes, the component responds by re-rendering.

    ```javascript
    //Correct
    this.setState({ message: 'Hello World' })
    ```

    **Note:** You can directly assign to the state object either in *constructor* or using latest javascript's class field declaration syntax.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

12. ### What is the purpose of callback function as an argument of `setState()`?
    The callback function is invoked when setState finished and the component gets rendered. Since `setState()` is **asynchronous** the callback function is used for any post action.

    **Note:** It is recommended to use lifecycle method rather than this callback function.

    ```javascript
    setState({ name: 'John' }, () => console.log('The name has updated and component re-rendered'))
    ```
    
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

13. ### What is the difference between HTML and React event handling?
    1. In HTML, the event name should be in *lowercase*:

    ```html
    <button onclick='activateLasers()'>
    ```

    Whereas in React it follows *camelCase* convention:

    ```jsx harmony
    <button onClick={activateLasers}>
    ```

    2. In HTML, you can return `false` to prevent default behavior:

    ```html
    <a href='#' onclick='console.log("The link was clicked."); return false;' />
    ```

    Whereas in React you must call `preventDefault()` explicitly:

    ```javascript
    function handleClick(event) {
      event.preventDefault()
      console.log('The link was clicked.')
    }
    ```

    3. In HTML, you need to invoke the function by appending `()`
    Whereas in react you should not append `()` with the function name. (refer "activateLasers" function in the first point for example)

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

14. ### How to bind methods or event handlers in JSX callbacks?
    There are 3 possible ways to achieve this:
    1.	**Binding in Constructor:** In JavaScript classes, the methods are not bound by default. The same thing applies for React event handlers defined as class methods. Normally we bind them in constructor.

    ```javascript
    class Component extends React.Componenet {
      constructor(props) {
        super(props)
        this.handleClick = this.handleClick.bind(this)
      }

      handleClick() {
        // ...
      }
    }
    ```

    2. **Public class fields syntax:** If you don't like to use bind approach then *public class fields syntax* can be used to correctly bind callbacks.

    ```jsx harmony
    handleClick = () => {
      console.log('this is:', this)
    }
    ```

    ```jsx harmony
    <button onClick={this.handleClick}>
      {'Click me'}
    </button>
    ```

    3. **Arrow functions in callbacks:** You can use *arrow functions* directly in the callbacks.

    ```jsx harmony
    <button onClick={(event) => this.handleClick(event)}>
      {'Click me'}
    </button>
    ```

    **Note:** If the callback is passed as prop to child components, those components might do an extra re-rendering. In those cases, it is preferred to go with `.bind()` or *public class fields syntax* approach considering performance.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

15. ### How to pass a parameter to an event handler or callback?
    You can use an *arrow function* to wrap around an *event handler* and pass parameters:

    ```jsx harmony
    <button onClick={() => this.handleClick(id)} />
    ```

    This is an equivalent to calling `.bind`:

    ```jsx harmony
    <button onClick={this.handleClick.bind(this, id)} />
    ```
    Apart from these two approaches, you can also pass arguments to a function which is defined as array function
    ```jsx harmony
    <button onClick={this.handleClick(id)} />
    handleClick = (id) => () => {
        console.log("Hello, your ticket number is", id)
    };
    ```
    
<div align="right">
    <b><a href="#">back to top</a></b>
</div>

16. ### What are synthetic events in React?

    `SyntheticEvent` is a cross-browser wrapper around the browser's native event. It's API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

17. ### What is inline conditional expressions?
    You can use either *if statements* or *ternary expressions* which are available from JS to conditionally render expressions. Apart from these approaches, you can also embed any expressions in JSX by wrapping them in curly braces and then followed by JS logical operator `&&`.

    ```jsx harmony
    <h1>Hello!</h1>
    {
        messages.length > 0 && !isLogin?
          <h2>
              You have {messages.length} unread messages.
          </h2>
          :
          <h2>
              You don't have unread messages.
          </h2>
    }
    ```

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

18. ### What are key props and what is the benefit of using them in arrays of elements?
    A `key` is a special string attribute you **should** include when creating arrays of elements. *Keys* help React identify which items have changed, are added, or are removed.

    Most often we use IDs from our data as *keys*:

    ```jsx harmony
    const todoItems = todos.map((todo) =>
      <li key={todo.id}>
        {todo.text}
      </li>
    )
    ```

    When you don't have stable IDs for rendered items, you may use the item *index* as a *key* as a last resort:

    ```jsx harmony
    const todoItems = todos.map((todo, index) =>
      <li key={index}>
        {todo.text}
      </li>
    )
    ```

    **Note:**
    1. Using *indexes* for *keys* is **not recommended** if the order of items may change. This can negatively impact performance and may cause issues with component state.
    2. If you extract list item as separate component then apply *keys* on list component instead of `li` tag.
    3. There will be a warning message in the console if the `key` prop is not present on list items.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

19. ### What is the use of refs?
    The *ref* is used to return a reference to the element. They *should be avoided* in most cases, however, they can be useful when you need a direct access to the DOM element or an instance of a component.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>
    
20. ### How to create refs?
    There are two approaches
    1. This is a recently added approach. *Refs* are created using `React.createRef()` method and attached to React elements via the `ref` attribute. In order to use *refs* throughout the component, just assign the *ref* to the instance property within constructor.

    ```jsx harmony
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)
        this.myRef = React.createRef()
      }
      render() {
        return <div ref={this.myRef} />
      }
    }
    ```
    2. You can also use ref callbacks approach regardless of React version. For example, the search bar component's input element accessed as follows,
    ```jsx harmony
    class SearchBar extends Component {
       constructor(props) {
          super(props);
          this.txtSearch = null;
          this.state = { term: '' };
          this.setInputSearchRef = e => {
             this.txtSearch = e;
          }
       }
       onInputChange(event) {
          this.setState({ term: this.txtSearch.value });
       }
       render() {
          return (
             <input
                value={this.state.term}
                onChange={this.onInputChange.bind(this)}
                ref={this.setInputSearchRef} />
          );
       }
    }
    ```

    You can also use *refs* in function components using **closures**.
    **Note**: You can also use inline ref callbacks even though it is not a recommended approach

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

21. ### What are forward refs?
    *Ref forwarding* is a feature that lets some components take a *ref* they receive, and pass it further down to a child.

    ```jsx harmony
    const ButtonElement = React.forwardRef((props, ref) => (
      <button ref={ref} className="CustomButton">
        {props.children}
      </button>
    ));

    // Create ref to the DOM button:
    const ref = React.createRef();
    <ButtonElement ref={ref}>{'Forward Ref'}</ButtonElement>
    ```

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

22. ### Which is preferred option with in callback refs and findDOMNode()?
    It is preferred to use *callback refs* over `findDOMNode()` API. Because `findDOMNode()` prevents certain improvements in React in the future.

    The **legacy** approach of using `findDOMNode`:

    ```javascript
    class MyComponent extends Component {
      componentDidMount() {
        findDOMNode(this).scrollIntoView()
      }

      render() {
        return <div />
      }
    }
    ```

    The recommended approach is:

    ```javascript
    class MyComponent extends Component {
      constructor(props){
        super(props);
        this.node = createRef();
      }
      componentDidMount() {
        this.node.current.scrollIntoView();
      }

      render() {
        return <div ref={this.node} />
      }
    }
    ```

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

23. ### Why are String Refs legacy?
    If you worked with React before, you might be familiar with an older API where the `ref` attribute is a string, like `ref={'textInput'}`, and the DOM node is accessed as `this.refs.textInput`. We advise against it because *string refs have below issues*, and are considered legacy. String refs were **removed in React v16**.

    1. They *force React to keep track of currently executing component*. This is problematic because it makes react module stateful, and thus causes weird errors when react module is duplicated in the bundle.
    2. They are *not composable* — if a library puts a ref on the passed child, the user can't put another ref on it. Callback refs are perfectly composable.
    3. They *don't work with static analysis* like Flow. Flow can't guess the magic that framework does to make the string ref appear on `this.refs`, as well as its type (which could be different). Callback refs are friendlier to static analysis.
    4. It doesn't work as most people would expect with the "render callback" pattern (e.g. <DataGrid renderRow={this.renderRow} />)
       ```jsx harmony
       class MyComponent extends Component {
         renderRow = (index) => {
           // This won't work. Ref will get attached to DataTable rather than MyComponent:
           return <input ref={'input-' + index} />;

           // This would work though! Callback refs are awesome.
           return <input ref={input => this['input-' + index] = input} />;
         }

         render() {
           return <DataTable data={this.props.data} renderRow={this.renderRow} />
         }
       }
       ```

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

24. ### What is Virtual DOM?
    The *Virtual DOM* (VDOM) is an in-memory representation of *Real DOM*. The representation of a UI is kept in memory and synced with the "real" DOM. It's a step that happens between the render function being called and the displaying of elements on the screen. This entire process is called *reconciliation*.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

25. ### How Virtual DOM works?
    The *Virtual DOM* works in three simple steps.
    1. Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
        ![vdom](images/vdom1.png)

    2. Then the difference between the previous DOM representation and the new one is calculated.
        ![vdom2](images/vdom2.png)

    3. Once the calculations are done, the real DOM will be updated with only the things that have actually changed.
        ![vdom3](images/vdom3.png)

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

26. ### What is the difference between Shadow DOM and Virtual DOM?
    The *Shadow DOM* is a browser technology designed primarily for scoping variables and CSS in *web components*. The *Virtual DOM* is a concept implemented by libraries in JavaScript on top of browser APIs.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

27. ### What is React Fiber?
    Fiber is the new *reconciliation* engine or reimplementation of core algorithm in React v16. The goal of React Fiber is to increase its suitability for areas like animation, layout, gestures, ability to pause, abort, or reuse work and assign priority to different types of updates; and new concurrency primitives.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

28. ### What is the main goal of React Fiber?
    The goal of *React Fiber* is to increase its suitability for areas like animation, layout, and gestures. Its headline feature is **incremental rendering**: the ability to split rendering work into chunks and spread it out over multiple frames.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

29. ### What are controlled components?
    A component that controls the input elements within the forms on subsequent user input is called **Controlled Component**, i.e, every state mutation will have an associated handler function.

    For example, to write all the names in uppercase letters, we use handleChange as below,

    ```javascript
    handleChange(event) {
      this.setState({value: event.target.value.toUpperCase()})
    }
    ```

<div align="right">
    <b><a href="#">back to top</a></b>
</div>

30. ### What are uncontrolled components?
    The **Uncontrolled Components** are the ones that store their own state internally, and you query the DOM using a ref to find its current value when you need it. This is a bit more like traditional HTML.

    In the below UserProfile component, the `name` input is accessed using ref.

    ```jsx harmony
    class UserProfile extends React.Component {
      constructor(props) {
        super(props)
        this.handleSubmit = this.handleSubmit.bind(this)
        this.input = React.createRef()
      }

      handleSubmit(event) {
        alert('A name was submitted: ' + this.input.current.value)
        event.preventDefault()
      }

      render() {
        return (
          <form onSubmit={this.handleSubmit}>
            <label>
              {'Name:'}
              <input type="text" ref={this.input} />
            </label>
            <input type="submit" value="Submit" />
          </form>
        );
      }
    }
    ```

    In most cases, it's recommend to use controlled components to implement forms.

<div align="right">
    <b><a href="#">back to top</a></b>
</div>
