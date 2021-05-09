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
