1. How would you refactor this code?
```jsx
class Button extends React.Component {
    constructor(props) {
        super(props);
    }
 
    render() {
        return (
            <button
                onClick={this.props.clickHandler}
                type="button">{this.props.text}</button>
        );
    }
}
```
---
2. What's wrong with this code?
```jsx
class Image extends React.Component {
    constructor(props) {
        super(props);
        this.state = { isImageLoaded : false };
        this.onImageLoad = this.onImageLoad.bind(this);
    }
    onImageLoad() {
        this.state.isImageLoaded = true;
    }
 
    render() {
        return (
            <img src={this.props.src} onLoad={this.onImageLoad} />
        );
    }  
}
```
---
3. What's the problem here?
```jsx
class Image extends React.Component {
    constructor(props) {
        super(props);
        this.onImageLoad = this.onImageLoad.bind(this);
    }
    onImageLoad() {
        this.setState({ isImageLoaded : true });
    }
 
    render() {
        this.setState({ isImageLoaded : false });  
        return (
            <img src={this.props.src} onLoad={this.onImageLoad} />
        );
    }
}
```
---
4. What's the problem with these callback bindings? Which one is a good solution?
```jsx
class Button extends React.Component {
    constructor(props) {
        super(props);
        this.onMouseMove = this.onMouseMove.bind(this);
    }
 
    render() {
        return (
            <button
                onMouseOver={this.onMouseOver}
                onMouseDown={() => this.onMouseDown()}
                onMouseEnter={function(event) { this.onMouseEnter(event) }}
                onMouseUp={this.onMouseUp.bind(this)}
                onMouseMove={this.onMouseMove}
                onClick={this.onClick}
            >Butt</button>
        );
    }
 
    onMouseOver(event) { console.log(event, this); }
    onMouseDown(event) { console.log(event, this); }
    onMouseEnter(event) { console.log(event, this); }
    onMouseUp(event) { console.log(event, this); }
    onMouseMove(event) { console.log(event, this); }
    onClick = (event) => { console.log(event, this); }
}
```
---
5. What warning will you get when you try to run this code? What's missing?
```jsx
const List = (props) => {
    const list = ['sorbet', 'gelato', 'tartufo'].map(item => (
        <li>{item}</li>
    ));
 
    return (
        <ul>{list}</ul>
    );
}
```
---
6. Why is this an anti-pattern? How would you refactor this component?
```jsx
const List = (props) => {
    const list = ['sorbet', 'gelato', 'tartufo'].map((item, index) => (
        <li key={index}>{item}</li>
    ));
 
    return (
        <ul>{list}</ul>
    );
}
```
---
7. Why void is needed here in this case?
What happens without it?
```jsx
useEffect(() => void setInterval(someFunction, 1000))
```
---
8. What are we trying to achieve by using the following line:
```js
let self = this;
```
- [ ] __a)__ By using let, it makes the value of this mutable, so that we can change its
properties
- [ ] __b)__ We assign the value of this to a variable to be able to use it when context
changes
- [ ] __c)__ By saving the value of this we enable the use of arrow functions to access
outer context
- [ ] __d)__ We cannot access this directly in strict mode, so we need to save a
reference to it
---
9. Which of these statements is true for JavaScript?
- [ ] __a)__ The value of "this" signifies the current context
- [ ] __b)__ The value of "this" signifies the current scope
- [ ] __c)__ You can modify the scope of a function using the .bind method
- [ ] __d)__ You can modify the context of a function using the .apply method
---
10. Which of the following can cause a memory leak?
- [ ] __a)__ Keeping references in scope for unused variables
- [ ] __b)__ Not removing event listeners before removing DOM nodes
- [ ] __c)__ Declaring variables with let in recursive function
- [ ] __d)__ Accidental assignment of variable on global context
---
11. What is true for the following code:
```js
let item, index = 0;
```
- [ ] __a)__ item is declared
- [ ] __b)__ item is not defined
- [ ] __c)__ index is not defined
- [ ] __d)__ items is not declared
- [ ] __e)__ index is declared and defined
- [ ] __f)__ item is null
---
12. Script tags that have the "defer" attribute
- [ ] __a)__ do not block rendering
- [ ] __b)__ keep the execution order of the scripts
- [ ] __c)__ are executed after the DOM is ready
- [ ] __d)__ work on inline script tags
---
13. By default when a click event is triggered on an element, it is also triggered on the element's ___
- [ ] __a)__ every descendant.
- [ ] __b)__ parent.
- [ ] __c)__ every ascendant.
- [ ] __d)__ child.
---
14. Check every property that will trigger a reflow in the browser when it changes:
- [ ] __a)__ z-index
- [ ] __b)__ overflow
- [ ] __c)__ font-family
- [ ] __d)__ text-rendering


