#update
$set is a command used for update.]

https://reactjs.org/docs/update.html


#Create-react-app
https://github.com/facebook/create-react-app

Using typescript
`npx create-react-app my-app --template typescript`

#Code splitting
	Different bundles
> dynamic import()
	Supported in Create React App.
	Webpack ref: https://webpack.js.org/guides/code-splitting/
> Suspense & Lazy loading
	Helpful for spinner.
> Error boundaries 	
> Route-based code splitting

```js
<Router>
    <Suspense fallback={<div>Loading...</div>}>
      <Switch>
        <Route exact path="/" component={Home}/>
        <Route path="/about" component={About}/>
      </Switch>
    </Suspense>
  </Router>
```
> Named Exports
	React.lazy currently only supports default exports. 

#Immutability
	"Time travel” feature	
	Determining When to Re-Render in React

#Key	
> When we render a list, React stores some information about each rendered list item. 
	When we update a list, React needs to determine what has changed.
	We could have added, removed, re-arranged, or updated the list’s items.
> Keys do not need to be globally unique; they only need to be unique between components and their siblings.


#React.Component
> The only method you must define in a React.Component subclass is called render(). 
> We strongly recommend against creating your own base component classes. 

> Cheatseett for component lifecycle
http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/	
> render()
	* The render() function should be pure, meaning that it does not modify component state, it returns the same result each time it’s invoked, and it does not directly interact with the browser.
	* render() will not be invoked if shouldComponentUpdate() returns false.
> constructor()
	If you don’t initialize state and you don’t bind (event)methods, you don’t need to implement a constructor for your React component.	
> componentDidMount()
	 If you need to load data from a remote endpoint, this is a good place to instantiate the network request.

> Haven't read the rest!
https://reactjs.org/docs/react-component.html

#4. Components and Props
Note: Always start component names with a capital letter.
> Props are Read-Only
	Whether you declare a component as a function or a class, it must never modify its own props. Consider this sum function:
>  All React components must act like pure functions with respect to their props.
```js
function sum(a, b) {
  return a + b;
}
```

#5. State and Lifecycle
setState():
> State Updates are Merged
> State Updates May Be Asynchronous

>setState()

#6. Handling Events
>Event Name: camelCase
`e.preventDefault();`

Bind a class to handleClick function. https://codepen.io/gaearon/pen/xEmzGg?editors=0010
```js
// This binding is necessary to make `this` work in the callback
this.handleClick = this.handleClick.bind(this);
...
<button onClick={this.handleClick}>
    {this.state.isToggleOn ? 'ON' : 'OFF'}
</button>
```

#7. Conditional Rendering
* Inline If with Logical && Operator
	`{unread.length > 0 && <h1> {unread.length} messages.</h1>}`
* Inline If-Else with Conditional Operator
	`condition ? true : false.`
* Preventing Component from Rendering
	`return null`

#8. Lists and Keys
> Key
	When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort.
	We don’t recommend using indexes for keys if the order of items may change.
https://medium.com/@robinpokorny/index-as-a-key-is-an-anti-pattern-e0349aece318

> Keys only make sense in the context of the surrounding array.
	A good rule of thumb is that elements inside the map() call need keys.
`<li key={value.toString()}>  {value}    </li>	` vs
`<ListItem key={number.toString()} value={number} />`
	 
> Keys Must Only Be Unique Among Siblings

> Keys serve as a hint to React but they don’t get passed to your components.
	A component can read props.id, but not props.key.
> Embedding map() in JSX
	Keep in mind that if the map() body is too nested, it might be a good time to extract a component.

#9. Forms
> Controlled Components
	An input form element whose value is controlled by React in this way is called a “controlled component”.
> Select
	You can pass an array into the value attribute, allowing you to select multiple options in a select tag:	
`<select multiple={true} value={['B', 'C']}>`
>  Uncontrolled component 
	Read-only : `<input type="file" />`
https://reactjs.org/docs/uncontrolled-components.html#the-file-input-tag


##GENERAL

#Lazy loading & 
Example
https://medium.com/hackernoon/lazy-loading-and-preloading-components-in-react-16-6-804de091c82d


#Bind
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind
* Bind a class for `this` to a func.
	funcA=classB.func;
	funcA.bind(classB); <-- `this` in classB.func(==funcA) will refer to classB.
* Pre-specify the initial arguments.
* Shortcut to a function which requires a specific this value.
	e.g: Array.prototype.slice()

> If calling bind annoys you, there are two ways you can get around this.
* Use Class fields when `public class fields syntax`
https://babeljs.io/docs/en/babel-plugin-transform-class-properties/
* Else, Arrow function in the callback:
	 In most cases, this is fine. However, if this callback is passed as a prop to lower components, those components might do an extra re-rendering.
	 We generally recommend binding in the constructor or using the class fields syntax, to avoid this sort of performance problem.
> Passing Arguments to Event Handlers
	arrow functions 
`<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>`
	Function.prototype.bind
`<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>`

