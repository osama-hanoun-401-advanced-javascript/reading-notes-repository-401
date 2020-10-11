## Props and State

**Forms and Input**

- React for elements maintain internal state. Think of React inputs as stateful child components. This means that we must manage the state of inputs through our own stateful component and one way data binding. The creation of a parent component (which we'll refer to as *form-container*), manages the state for all child components of the form and passes any necessary state down into its inputs through the use of `props`. Each input has an `onChange` event that we can handle and use to update our form-container's state each time the user interacts with an input.

**Props**

- Components accept arbitrary inputs called `props`. In JSX, props are passed into a component with a syntax that looks like HTML attributes. These are the equivalent of function params.

- In actuality, `props` is the name of the object passed into a component constructor and any prop added to a component in the JSX will be accessible as a property on `props`.

- After `props` is passed into the constructor's `super` function, they are available on the context by using `this.props`.

**Props can be data or functions**

- In JavaScript, we can pass functions around like variables. We've been doing this all along (named callback functions in express and jQuery, for example). Now we get to really harness that power!

- When this renders...

  - Foo will draw Bar

  - Bar will draw a button

  - When that button gets clicked, its `onClick` action fires

    - That action runs the method `this.props.handleClick`

    - That method runs in `<Foo>`---`<Foo>` passed it down to `<Bar>` essentially telling it what it wants it to do.

  - This is a means of passing not only **Data** but **Behavior** down the component tree

```
class Foo extends React.Component {
  constructor(props){
    super(props)
  }

  screamLoud() {
    console.log("OUCH");
  }

  render(){
    return (
      <div>
        <Bar handleClick={this.screamLoud} />
      </div>
    )
  }
}

class Bar extends React.Component {

  constructor(props) {
    super(props);
  }

  render() {
    <div>
      <button onClick={this.props.handleClick}>Click</button>
    </div>
  }

}
```

**One Way Data Flow**

- State can only be passed from parent component to a child component through the use of `props`. This enforces the idea of one way data flow. One way data flow is a way of describing that state can only be passed down the component tree (not up). If a child wants to pass some data to a parent, the parent can pass a functionto the child through `props` and the child may invoke that function and pass it data for the parent to manage.
