# REACT

This appendix is a non-exhaustive list of new syntactic features and methods that were added to JavaScript in ES6. These features are the most commonly used and most helpful.

While this appendix doesn't cover ES6 classes, we go over the basics while learning about components in the book. In addition, this appendix doesn't include descriptions of some larger new features like promises and generators. If you'd like more info on those or on any topic below, we encourage you to reference the [Mozilla Developer Network's website](https://developer.mozilla.org/) \(MDN\).

#### Prefer `const` and `let` over `var`

If you've worked with ES5 JavaScript before, you're likely used to seeing variables declared with `var`:

```javascript
var myVariable = 5;
```

Both the `const` and `let` statements also declare variables. They were introduced in ES6.

Use `const` in cases where a variable is never re-assigned. Using `const` makes this clear to whoever is reading your code. It refers to the "constant" state of the variable in the context it is defined within.

If the variable will be re-assigned, use `let`.

We encourage the use of `const` and `let` instead of `var`. In addition to the restriction introduced by `const`, both `const` and `let` are _block scoped_ as opposed to _function scoped_. This scoping can help avoid unexpected bugs.

#### Arrow functions

There are three ways to write arrow function bodies. For the examples below, let's say we have an array of city objects:

```javascript
onst cities = [
  { name: 'Cairo', pop: 7764700 },
  { name: 'Lagos', pop: 8029200 },
];
```

If we write an arrow function that spans multiple lines, we must use braces to delimit the function body like this:

```javascript
const formattedPopulations = cities.map((city) => {
  const popMM = (city.pop / 1000000).toFixed(2);
  return popMM + ' million';
});
console.log(formattedPopulations);
```

Note that we must also explicitly specify a `return` for the function.

However, if we write a function body that is only a single line \(or single expression\) we can use parentheses to delimit it:

```javascript
const formattedPopulations2 = cities.map((city) => (
  (city.pop / 1000000).toFixed(2) + ' million'
));
```

Notably, we don't use `return` as it's implied.

Furthermore, if your function body is terse you can write it like so:

```javascript
const pops = cities.map(city => city.pop);
console.log(pops);
```

The terseness of arrow functions is one of two reasons that we use them. Compare the one-liner above to this:

```javascript
const popsNoArrow = cities.map(function(city) { return city.pop });
```

Of greater benefit, though, is how arrow functions bind the `this` object.

The traditional JavaScript function declaration syntax \(`function () {}`\) will bind `this` in anonymous functions to the global object. To illustrate the confusion this causes, consider the following example:

```javascript
unction printSong() {
  console.log("Oops - The Global Object");
}

const jukebox = {
  songs: [
    {
      title: "Wanna Be Startin' Somethin'",
      artist: "Michael Jackson",
    },
    {
      title: "Superstar",
      artist: "Madonna",
    },
  ],
  printSong: function (song) {
    console.log(song.title + " - " + song.artist);
  },
  printSongs: function () {

    this.songs.forEach(function(song) {

      this.printSong(song);
    });
  },
}

jukebox.printSongs();
```

The method `printSongs()` iterates over `this.songs` with `forEach()`. In this context, `this` is bound to the object \(`jukebox`\) as expected. However, the anonymous function passed to `forEach()` binds its internal `this` to the global object. As such, `this.printSong(song)` calls the function declared at the top of the example, _not_ the method on `jukebox`.

JavaScript developers have traditionally used workarounds for this behavior, but arrow functions solve the problem by **capturing the `this` value of the enclosing context**. Using an arrow function for `printSongs()` has the expected result:

```javascript
  printSongs: function () {
    this.songs.forEach((song) => {

      this.printSong(song);
    });
  },
}

jukebox.printSongs();
```

For this reason, throughout the book we use arrow functions for all anonymous functions.

#### Modules

ES6 formally supports modules using the `import`/`export` syntax.

**Named exports**

Inside any file, you can use `export` to specify a variable the module should expose. Here's an example of a file that exports two functions:

```javascript
export const sayHi = () => (console.log('Hi!'));
export const sayBye = () => (console.log('Bye!'));

const saySomething = () => (console.log('Something!'));
```

Now, anywhere we wanted to use these functions we could use `import`. We need to specify which functions we want to import. A common way of doing this is using ES6's destructuring assignment syntax to list them out like this:

```javascript
import { sayHi, sayBye } from './greetings';

sayHi(); 
sayBye();
```

Importantly, the function that was _not_ exported \(`saySomething`\) is unavailable outside of the module.

Also note that we supply a **relative path** to `from`, indicating that the ES6 module is a local file as opposed to an npm package.

Instead of inserting an `export` before each variable you'd like to export, you can use this syntax to list off all the exposed variables in one area:

```javascript
const sayHi = () => (console.log('Hi!'));
const sayBye = () => (console.log('Bye!'));

const saySomething = () => (console.log('Something!'));

export { sayHi, sayBye };
```

We can also specify that we'd like to import all of a module's functionality underneath a given namespace with the `import * as <Namespace>` syntax:

```javascript
import * as Greetings from './greetings';

Greetings.sayHi();

Greetings.sayBye();

Greetings.saySomething();
```

**Default export**

The other type of export is a default export. A module can only contain one default export:

```javascript
const sayHi = () => (console.log('Hi!'));
const sayBye = () => (console.log('Bye!'));

const saySomething = () => (console.log('Something!'));

const Greetings = { sayHi, sayBye };

export default Greetings;
```

This is a common pattern for libraries. It means you can easily import the library wholesale without specifying what individual functions you want:

```javascript
import Greetings from './greetings';

Greetings.sayHi(); 
Greetings.sayBye();
```

It's not uncommon for a module to use a mix of both named exports and default exports. For instance, with `react-dom`, you can import `ReactDOM` \(a default export\) like this:

```javascript
import ReactDOM from 'react-dom';

ReactDOM.render(

);
```

Or, if you're only going to use the `render()` function, you can import the named `render()` function like this:

```javascript
import { render } from 'react-dom';

render(

);
```

To achieve this flexibility, the export implementation for `react-dom` looks something like this:

```javascript
export const render = (component, target) => {

};

const ReactDOM = {
  render,

};

export default ReactDOM;
```

If you want to play around with the module syntax, check out the folder `code/webpack/es6-modules`.

For more reading on ES6 modules, see this article from Mozilla: "[ES6 in Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)".

#### `Object.assign()`

We use `Object.assign()` often throughout the book. We use it in areas where we want to create a modified version of an existing object.

`Object.assign()` accepts any number of objects as arguments. When the function receives two arguments, it _copies_ the properties of the second object onto the first, like so:

```javascript
onst coffee = { };
const noCream = { cream: false };
const noMilk = { milk: false };
Object.assign(coffee, noCream);
```

It is idiomatic to pass in three arguments to `Object.assign()`. The first argument is a new JavaScript object, the one that `Object.assign()` will ultimately return. The second is the object whose properties we'd like to build off of. The last is the changes we'd like to apply:

```javascript
const coffeeWithMilk = Object.assign({}, coffee, { milk: true });
```

`Object.assign()` is a handy method for working with "immutable" JavaScript objects.

#### Template literals

In ES5 JavaScript, you'd interpolate variables into strings like this:

```javascript
var greeting = 'Hello, ' + user + '! It is ' + degF + ' degrees outside.';
```

With ES6 template literals, we can create the same string like this:

```javascript
const greeting = `Hello, ${user}! It is ${degF} degrees outside.`;
```

#### The spread operator \(`...`\)

In arrays, the ellipsis `...` operator will _expand_ the array that follows into the parent array. The spread operator enables us to succinctly construct new arrays as a composite of existing arrays.

Here is an example:

```javascript
const a = [ 1, 2, 3 ];
const b = [ 4, 5, 6 ];
const c = [ ...a, ...b, 7, 8, 9 ];

console.log(c);
```

Notice how this is different than if we wrote:

```javascript
const d = [ a, b, 7, 8, 9 ];
console.log(d);
```

#### Enhanced object literals

In ES5, all objects were required to have explicit key and value declarations:

```javascript
const explicit = {
  getState: getState,
  dispatch: dispatch,
};
```

In ES6, you can use this terser syntax whenever the property name and variable name are the same:

```javascript
const implicit = {
  getState,
  dispatch,
};
```

Lots of open source libraries use this syntax, so it's good to be familiar with it. But whether you use it in your own code is a matter of stylistic preference.

#### Default arguments

With ES6, you can specify a default value for an argument in the case that it is `undefined` when the function is called.

This:

```javascript
unction divide(a, b) {

  const divisor = typeof b === 'undefined' ? 1 : b;

  return a / divisor;
}
```

Can be written as this:

```javascript
function divide(a, b = 1) {
  return a / b;
}
```

In both cases, using the function looks like this:

```javascript
divide(14, 2);

divide(14, undefined);

divide(14);
```

Whenever the argument `b` in the example above is `undefined`, the default argument is used. Note that `null` will not use the default argument:

```javascript
divide(14, null);
```

#### Destructuring assignments

**For arrays**

In ES5, extracting and assigning multiple elements from an array looked like this:

```javascript
ar fruits = [ 'apples', 'bananas', 'oranges' ];
var fruit1 = fruits[0];
var fruit2 = fruits[1];
```

In ES6, we can use the destructuring syntax to accomplish the same task like this:

```javascript
const [ veg1, veg2 ] = [ 'asparagus', 'broccoli', 'onion' ];
console.log(veg1); 
console.log(veg2);
```

The variables in the array on the left are "matched" and assigned to the corresponding elements in the array on the right. Note that `'onion'` is ignored and has no variable bound to it.

**For objects**

We can do something similar for extracting object properties into variables:

```javascript
const smoothie = {
  fats: [ 'avocado', 'peanut butter', 'greek yogurt' ],
  liquids: [ 'almond milk' ],
  greens: [ 'spinach' ],
  fruits: [ 'blueberry', 'banana' ],
};

const { liquids, fruits } = smoothie;

console.log(liquids); 
console.log(fruits);
```

**Parameter context matching**

We can use these same principles to bind arguments inside a function to properties of an object supplied as an argument:

```javascript
const containsSpinach = ({ greens }) => {
  if (greens.find(g => g === 'spinach')) {
    return true;
  } else {
    return false;
  }
};

containsSpinach(smoothie);
```

We do this often with functional React components:

```javascript
const IngredientList = ({ ingredients, onClick }) => (
  <ul className='IngredientList'>
    {
      ingredients.map(i => (
        <li
          key={i.id}
          onClick={() => onClick(i.id)}
          className='item'
        >
          {i.name}
        </li>
      ))
    }
  </ul>
)
```

Here, we use destructuring to extract the props into variables \(`ingredients` and `onClick`\) that we then use inside the component's function body.







## React.js cheatsheet

> React.Component · render\(\) · componentDidMount\(\) · props/state · dangerouslySetInnerHTML · React is a JavaScript library for building user interfaces. This guide targets React v15 to v16.

[React](https://reactjs.org/) is a JavaScript library for building user interfaces. This guide targets React v15 to v16.

## React Cheat Sheet

### render

```text
render() {
  return <div />;
}
```

### constructor

```javascript
    constructor(props) {
      super(props);
      this.state = {
        list: props.initialList
      };
    }

    // where props aren't used in constructor

    constructor() {
      super();
      this.state = {
        list: []
      };
    }
```

### componentWillMount

```javascript
    componentWillMount() {
      // invoked once.
      // fires before initial 'render'
    }
```

### componentDidMount

```javascript
    componentDidMount() {
      // good for AJAX: fetch, ajax, or subscriptions.

      // invoked once (client-side only).
      // fires before initial 'render'
    }
```

### componentWillReceiveProps

```javascript
    componentWillReceiveProps(nextProps) {
      // invoked every time component recieves new props.
      // does not before initial 'render'
    }
```

### shouldComponentUpdate

```javascript
    shouldComponentUpdate(nextProps, nextState) {
      // invoked before every update (new props or state).
      // does not fire before initial 'render'.
    }
```

### componentWillUpdate

```javascript
    componentWillUpdate(nextProps, nextState) {
      // invoked immediately before update (new props or state).
      // does not fire before initial 'render'.

      // (see componentWillReceiveProps if you need to call setState)
    }
```

**✖ this.setState**

### componentDidUpdate

```javascript
    componentDidUpdate(prevProps, prevState) {
      // invoked immediately after DOM updates
      // does not fire after initial 'render'
    }
```

### componentWillUnmount

```javascript
    componentWillUnmount() {
      // invoked immediately before a component is unmounted.
    }
```

### setState \(function\)

```javascript
    // good for state transitions

    this.setState((prevState, props) => {
      return {count: prevState.count + props.step};
    });
```

### setState \(object\)

```javascript
    // good for static values

    this.setState({mykey: 'my new value'});
```

### setState \(optional callback\)

```javascript
    // fires after setState
    // prefer componentDidUpdate

    this.setState(
      (prevState, props) => ({ count: prevState.count + props.step }),
      () => console.log(this.state.count)
    );
```

### forceUpdate

```javascript
    // forces a re-render; AVOID if possible

    this.forceUpdate();
```

### displayName

```javascript
    displayName: "MyComponent"
```

### defaultProps

```javascript
    class Greeting extends React.Component {
          render() {
            return <h1>Hi {this.props.name}</h1>
          }
        }

        CustomButton.defaultProps = {
          name: 'guest'
        };
```

### Children.map

```javascript
    React.Children.map(this.props.children, (child, i) => {
        return child;
    })
```

### Children.forEach

```javascript
    React.Children.forEach(this.props.children, (child, i) => {
      console.log(child + ' at index: ' + i);
    })
```

### Children.count

```javascript
    React.Children.count(this.props.children);
```

### Children.only

```javascript
    React.Children.only(this.props.children);
```

### Children.toArray

```javascript
    React.Children.toArray(this.props.children)
```

### Context \(example\)

```javascript
    // requires 'prop-types' library

    import { string } from "prop-types";

    class Cowboy extends React.Component {
      childContextTypes: {
        salutation: string
      }

      getChildContext() {
        return { salutation: "Howdy" };
      }

      render() {
        return React.Children.only(this.props.children);
      }
    }

    const Greeting = (props, context) =>
      <div>{context.salutation} {props.name}.</div>

    Greeting.contextTypes = {
      salutation: PropTypes.string
    }

    // <Greeting name="Michael" />
    // => Michael.

    // <Cowboy><Greeting name="Michael" /></Cowboy>
    // => Howdy Michael.
```

### contextTypes

```javascript
    // add to the context-aware component
    // requires 'prop-types' library

    contextTypes: {
      color: PropTypes.string
    },
```

### childContextTypes

```javascript
    // add to the context provider
    // requires 'prop-types' library

    childContextTypes: {
      color: PropTypes.string
    },
```

### getChildContext

```javascript
    // add to the context provider

    getChildContext() {
      return {color: "purple"};
    }
```

### \#Components

#### Components

```javascript
    import React from 'react'
    import ReactDOM from 'react-dom'


    class Hello extends React.Component {
      render () {
        return <div className='message-box'>
          Hello {this.props.name}
        </div>
      }
    }


    const el = document.body
    ReactDOM.render(<Hello name='John' />, el)
```

Use the [React.js jsfiddle](https://jsfiddle.net/reactjs/69z2wepo/) to start hacking. \(or the unofficial [jsbin](http://jsbin.com/yafixat/edit?js,output)\)

#### Import multiple exports

```javascript
    import React, {Component} from 'react'
    import ReactDOM from 'react-dom'


    class Hello extends Component {
      ...
    }
```

#### Properties

```javascript
    <Video fullscreen={true} autoplay={false} />


    render () {
      this.props.fullscreen
      const { fullscreen, autoplay } = this.props
      ···
    }
```

Use `this.props` to access properties passed to the component.

See: [Properties](https://reactjs.org/docs/tutorial.html#using-props)

#### States

```javascript
    constructor(props) {
      super(props)
      this.state = { username: undefined }
    }


    this.setState({ username: 'rstacruz' })


    render () {
      this.state.username
      const { username } = this.state
      ···
    }
```

Use states \(`this.state`\) to manage dynamic data.

With [Babel](https://babeljs.io/) you can use [proposal-class-fields](https://github.com/tc39/proposal-class-fields) and get rid of constructor

```javascript
    class Hello extends Component {
      state = { username: undefined };
      ...
    }
```

See: [States](https://reactjs.org/docs/tutorial.html#reactive-state)

#### Nesting

```javascript
    class Info extends Component {
      render () {
        const { avatar, username } = this.props

        return <div>
          <UserAvatar src={avatar} />
          <UserProfile username={username} />
        </div>
      }
    }
```

As of React v16.2.0, fragments can be used to return multiple children without adding extra wrapping nodes to the DOM.

```javascript
    import React, {
      Component,
      Fragment
    } from 'react'

    class Info extends Component {
      render () {
        const { avatar, username } = this.props

        return (
          <Fragment>
            <UserAvatar src={avatar} />
            <UserProfile username={username} />
          </Fragment>
        )
      }
    }
```

Nest components to separate concerns.

See: [Composing Components](https://reactjs.org/docs/components-and-props.html#composing-components)

#### Children

```javascript
    <AlertBox>
      <h1>You have pending notifications</h1>
    </AlertBox>


    class AlertBox extends Component {
      render () {
        return <div className='alert-box'>
          {this.props.children}
        </div>
      }
    }
```

Children are passed as the `children` property.

### \#Defaults

#### Setting default props

```javascript
    Hello.defaultProps = {
      color: 'blue'
    }
```

See: [defaultProps](https://reactjs.org/docs/react-component.html#defaultprops)

#### Setting default state

```javascript
    class Hello extends Component {
      constructor (props) {
        super(props)
        this.state = { visible: true }
      }
    }
```

Set the default state in the `constructor()`.

And without constructor using [Babel](https://babeljs.io/) with [proposal-class-fields](https://github.com/tc39/proposal-class-fields).

```javascript
    class Hello extends Component {
      state = { visible: true }
    }
```

See: [Setting the default state](https://reactjs.org/docs/react-without-es6.html#setting-the-initial-state)

### \#Other components

#### Functional components

```javascript
    function MyComponent ({ name }) {
      return <div className='message-box'>
        Hello {name}
      </div>
    }
```

Functional components have no state. Also, their `props` are passed as the first parameter to a function.

See: [Function and Class Components](https://reactjs.org/docs/components-and-props.html#functional-and-class-components)

#### Pure components

```javascript
    import React, {PureComponent} from 'react'

    class MessageBox extends PureComponent {
      ···
    }
```

Performance-optimized version of `React.Component`. Doesn’t rerender if props/state hasn’t changed.

See: [Pure components](https://reactjs.org/docs/react-api.html#react.purecomponent)

#### Component API

```javascript
    this.forceUpdate()


    this.setState({ ... })
    this.setState(state => { ... })


    this.state
    this.props
```

These methods and properties are available for `Component` instances.

See: [Component API](https://facebook.github.io/react/docs/component-api.html)

### \#Lifecycle

#### Mounting

| Method | Description |
| :--- | :--- |
| `constructor` _\(props\)_ | Before rendering [\#](https://reactjs.org/docs/react-component.html#constructor) |
| `componentWillMount()` | _Don’t use this_ [\#](https://reactjs.org/docs/react-component.html#componentwillmount) |
| `render()` | Render [\#](https://reactjs.org/docs/react-component.html#render) |
| `componentDidMount()` | After rendering \(DOM available\) [\#](https://reactjs.org/docs/react-component.html#componentdidmount) |
| `componentWillUnmount()` | Before DOM removal [\#](https://reactjs.org/docs/react-component.html#componentwillunmount) |
| `componentDidCatch()` | Catch errors \(16+\) [\#](https://reactjs.org/blog/2017/07/26/error-handling-in-react-16.html) |

Set initial the state on `constructor()`. Add DOM event handlers, timers \(etc\) on `componentDidMount()`, then remove them on `componentWillUnmount()`.

#### Updating

| Method | Description |
| :--- | :--- |
| `componentDidUpdate` _\(prevProps, prevState, snapshot\)_ | Use `setState()` here, but remember to compare props |
| `shouldComponentUpdate` _\(newProps, newState\)_ | Skips `render()` if returns false |
| `render()` | Render |
| `componentDidUpdate` _\(prevProps, prevState\)_ | Operate on the DOM here |

Called when parents change properties and `.setState()`. These are not called for initial renders.

See: [Component specs](https://facebook.github.io/react/docs/component-specs.html#updating-componentwillreceiveprops)

### \#Hooks \(New\)

#### State Hook

```javascript
    import React, { useState } from 'react';

    function Example() {

      const [count, setCount] = useState(0);

      return (
        <div>
          <p>You clicked {count} times</p>
          <button onClick={() => setCount(count + 1)}>
            Click me
          </button>
        </div>
      );
    }
```

Hooks are a new addition in React 16.8.

See: [Hooks at a Glance](https://reactjs.org/docs/hooks-overview.html)

#### Declaring multiple state variables

```javascript
    function ExampleWithManyStates() {

      const [age, setAge] = useState(42);
      const [fruit, setFruit] = useState('banana');
      const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);

    }
```

#### Effect hook

```javascript
    import React, { useState, useEffect } from 'react';

    function Example() {
      const [count, setCount] = useState(0);


      useEffect(() => {

        document.title = `You clicked ${count} times`;
      }, [count]);

      return (
        <div>
          <p>You clicked {count} times</p>
          <button onClick={() => setCount(count + 1)}>
            Click me
          </button>
        </div>
      );
    }
```

If you’re familiar with React class lifecycle methods, you can think of `useEffect` Hook as `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` combined.

By default, React runs the effects after every render — including the first render.

#### Building your own hooks

**Define FriendStatus**

```javascript
    import React, { useState, useEffect } from 'react';

    function FriendStatus(props) {
      const [isOnline, setIsOnline] = useState(null);

      useEffect(() => {
        function handleStatusChange(status) {
          setIsOnline(status.isOnline);
        }

        ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
        return () => {
          ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
        };
      }, [props.friend.id]);

      if (isOnline === null) {
        return 'Loading...';
      }
      return isOnline ? 'Online' : 'Offline';
    }
```

Effects may also optionally specify how to “clean up” after them by returning a function.

**Use FriendStatus**

```javascript
    function FriendStatus(props) {
      const isOnline = useFriendStatus(props.friend.id);

      if (isOnline === null) {
        return 'Loading...';
      }
      return isOnline ? 'Online' : 'Offline';
    }
```

See: [Building Your Own Hooks](https://reactjs.org/docs/hooks-custom.html)

#### Hooks API Reference

Also see: [Hooks FAQ](https://reactjs.org/docs/hooks-faq.html)

**Basic Hooks**

| Hook | Description |
| :--- | :--- |
| `useState`_\(initialState\)_ |  |
| `useEffect`_\(\(\) =&gt; { … }\)_ |  |
| `useContext`_\(MyContext\)_ | value returned from `React.createContext` |

Full details: [Basic Hooks](https://reactjs.org/docs/hooks-reference.html#basic-hooks)

**Additional Hooks**

| Hook | Description |
| :--- | :--- |
| `useReducer`_\(reducer, initialArg, init\)_ |  |
| `useCallback`_\(\(\) =&gt; { … }\)_ |  |
| `useMemo`_\(\(\) =&gt; { … }\)_ |  |
| `useRef`_\(initialValue\)_ |  |
| `useImperativeHandle`_\(ref, \(\) =&gt; { … }\)_ |  |
| `useLayoutEffect` | identical to `useEffect`, but it fires synchronously after all DOM mutations |
| `useDebugValue`_\(value\)_ | display a label for custom hooks in React DevTools |

Full details: [Additional Hooks](https://reactjs.org/docs/hooks-reference.html#additional-hooks)

### \#DOM nodes

#### References

```javascript
    class MyComponent extends Component {
      render () {
        return <div>
          <input ref={el => this.input = el} />
        </div>
      }

      componentDidMount () {
        this.input.focus()
      }
    }
```

Allows access to DOM nodes.

See: [Refs and the DOM](https://reactjs.org/docs/refs-and-the-dom.html)

#### DOM Events

```javascript
    class MyComponent extends Component {
      render () {
        <input type="text"
            value={this.state.value}
            onChange={event => this.onChange(event)} />
      }

      onChange (event) {
        this.setState({ value: event.target.value })
      }
    }
```

Pass functions to attributes like `onChange`.

See: [Events](https://reactjs.org/docs/events.html)

### \#Other features

#### Transferring props

```javascript
    <VideoPlayer src="video.mp4" />


    class VideoPlayer extends Component {
      render () {
        return <VideoEmbed {...this.props} />
      }
    }
```

Propagates `src="..."` down to the sub-component.

See [Transferring props](https://facebook.github.io/react/docs/transferring-props.html)

#### Top-level API

```javascript
    React.createClass({ ... })
    React.isValidElement(c)


    ReactDOM.render(<Component />, domnode, [callback])
    ReactDOM.unmountComponentAtNode(domnode)


    ReactDOMServer.renderToString(<Component />)
    ReactDOMServer.renderToStaticMarkup(<Component />)
```

There are more, but these are most common.

See: [React top-level API](https://reactjs.org/docs/react-api.html)

### \#JSX patterns

#### Style shorthand

```javascript
    const style = { height: 10 }
    return <div style={style}></div>


    return <div style={{ margin: 0, padding: 0 }}></div>
```

See: [Inline styles](https://reactjs.org/tips/inline-styles.html)

#### Inner HTML

```javascript
    function markdownify() { return "<p>...</p>"; }
    <div dangerouslySetInnerHTML={{__html: markdownify()}} />
```

See: [Dangerously set innerHTML](https://reactjs.org/tips/dangerously-set-inner-html.html)

#### Lists

```javascript
    class TodoList extends Component {
      render () {
        const { items } = this.props

        return <ul>
          {items.map(item =>
            <TodoItem item={item} key={item.key} />)}
        </ul>
      }
    }
```

Always supply a `key` property.

#### Conditionals

```javascript
    <Fragment>
      {showMyComponent
        ? <MyComponent />
        : <OtherComponent />}
    </Fragment>
```

#### Short-circuit evaluation

```javascript
    <Fragment>
      {showPopup && <Popup />}
      ...
    </Fragment>
```

### \#New features

#### Returning multiple elements

You can return multiple elements as arrays or fragments.

**Arrays**

```javascript
    render () {

      return [
        <li key="A">First item</li>,
        <li key="B">Second item</li>
      ]
    }
```

**Fragments**

```javascript
    render () {

      return (
        <Fragment>
          <li>First item</li>
          <li>Second item</li>
        </Fragment>
      )
    }
```

See: [Fragments and strings](https://reactjs.org/blog/2017/09/26/react-v16.0.html#new-render-return-types-fragments-and-strings)

#### Returning strings

```javascript
    render() {
      return 'Look ma, no spans!';
    }
```

You can return just a string.

See: [Fragments and strings](https://reactjs.org/blog/2017/09/26/react-v16.0.html#new-render-return-types-fragments-and-strings)

#### Errors

```javascript
    class MyComponent extends Component {
      ···
      componentDidCatch (error, info) {
        this.setState({ error })
      }
    }
```

Catch errors via `componentDidCatch`. \(React 16+\)

See: [Error handling in React 16](https://reactjs.org/blog/2017/07/26/error-handling-in-react-16.html)

#### Portals

```javascript
    render () {
      return React.createPortal(
        this.props.children,
        document.getElementById('menu')
      )
    }
```

This renders `this.props.children` into any location in the DOM.

See: [Portals](https://reactjs.org/docs/portals.html)

#### Hydration

```javascript
    const el = document.getElementById('app')
    ReactDOM.hydrate(<App />, el)
```

Use `ReactDOM.hydrate` instead of using `ReactDOM.render` if you’re rendering over the output of [ReactDOMServer](https://reactjs.org/docs/react-dom-server.html).

See: [Hydrate](https://reactjs.org/docs/react-dom.html#hydrate)

### \#Property validation

#### PropTypes

```javascript
    import PropTypes from 'prop-types'
```

See: [Typechecking with PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)

| Key | Description |
| :--- | :--- |
| `any` | Anything |

**Basic**

| Key | Description |
| :--- | :--- |
| `string` |  |
| `number` |  |
| `func` | Function |
| `bool` | True or false |

**Enum**

| Key | Description |
| :--- | :--- |
| `oneOf`_\(any\)_ | Enum types |
| `oneOfType`_\(type array\)_ | Union |

**Array**

| Key | Description |
| :--- | :--- |
| `array` |  |
| `arrayOf`_\(…\)_ |  |

**Object**

| Key | Description |
| :--- | :--- |
| `object` |  |
| `objectOf`_\(…\)_ | Object with values of a certain type |
| `instanceOf`_\(…\)_ | Instance of a class |
| `shape`_\(…\)_ |  |

**Elements**

| Key | Description |
| :--- | :--- |
| `element` | React element |
| `node` | DOM node |

**Required**

| Key | Description |
| :--- | :--- |
| `(···).isRequired` | Required |

#### Basic types

```javascript
    MyComponent.propTypes = {
      email:      PropTypes.string,
      seats:      PropTypes.number,
      callback:   PropTypes.func,
      isClosed:   PropTypes.bool,
      any:        PropTypes.any
    }
```

#### Required types

```javascript
    MyCo.propTypes = {
      name:  PropTypes.string.isRequired
    }
```

#### Elements

```javascript
    MyCo.propTypes = {

      element: PropTypes.element,


      node: PropTypes.node
    }
```

#### Enumerables \(oneOf\)

```javascript
    MyCo.propTypes = {
      direction: PropTypes.oneOf([
        'left', 'right'
      ])
    }
```

#### Arrays and objects

```javascript
    MyCo.propTypes = {
      list: PropTypes.array,
      ages: PropTypes.arrayOf(PropTypes.number),
      user: PropTypes.object,
      user: PropTypes.objectOf(PropTypes.number),
      message: PropTypes.instanceOf(Message)
    }


    MyCo.propTypes = {
      user: PropTypes.shape({
        name: PropTypes.string,
        age:  PropTypes.number
      })
    }
```

Use `.array[Of]`, `.object[Of]`, `.instanceOf`, `.shape`.

#### Custom validation

```javascript
    MyCo.propTypes = {
      customProp: (props, key, componentName) => {
        if (!/matchme/.test(props[key])) {
          return new Error('Validation failed!')
        }
      }
    }
```

