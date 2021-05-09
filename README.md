How would you refactor this code?

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
