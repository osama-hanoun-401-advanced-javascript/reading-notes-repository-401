## Application State with Redux

- Managing state with Redux requires the combination of three distinct aspects into a "Store" which all components can access as they please.

  - State

  - Reducers (strategies to alter state)

  - Actions (methods that get "dispatched" or "run", which trigger associated reducers)

**Redux Store**

- Ultimately, the “store” is where your application state is, well, stored. The store’s job is to identify the various reducers and middleware that need to be made available and used globally.

- React uses “reducers” to hold and manage state. Reducers typically manage just one part of the larger application state. For example, in a storefront application, you would likely have a separate reducer for Products, Categories, and Carts.

- Here’s a sample reducer for a shopping cart. As you can see it creates an initial “empty” state, and then identifies what to do when a certain action (e.g. INITIALIZE) is called. Reducers always “Hear” that an action was dispatched, and use whatever “payload” they receive to do their work.

```
let initialState = { customerId: null, items: [] };

const myReducer = (state = initialState, action) => {
  let { type, payload } = action;

  switch (type) {
    case 'INITIALIZE':
      return {customerId: payload.id};

    case 'ADD_ITEM':
      return { items: [...items, payload.item] };

    case 'CLEAR':
      return initialState;

    default:
      return state;
  }
};
```

- React applications with Redux dispatch “actions” (like an event) with “payload” (data). An action creator function as shown below always returns an action object with the action type to perform and the data to perform it with. When your component wants to modify state, it “Dispatches” (calls) an action and sends whatever payload (data) it needs to, to the reducer.

- When an action is dispatched, a reducer responds to it, and receives that payload, where it then operates on state using it.

```
// actions.js
const newCart = customer => {
  return {
    type: 'INITIALIZE',
    payload: customer,
  };
};
```

- We use a store to “bring it all together” … in the store, you declare what middleware you may need and the reducers that you’ll use to manage your state data.

```
import { createStore, combineReducers, applyMiddleware } from 'redux';

import cartReducer from './reducers/cart.js';

let reducers = combineReducers({
  cart: cartReducer,
});

export default () => createStore(reducers);
```

- Components subscribe to the store and get to use actions with a bit of boilerplate code:

- In this example, when the 'Start Shopping' button is clicked, it runs a method called `this.props.initializeTheCart()`.

- This method is declared in the `mapDispatchToProps` function as a pointer to the `newCart()` method in the actions file.

- When you do this, you get to use `this.props.initializeTheCart` as a method. That's what the mapper does for youo, along with mapping the reducer's state to `this.props` with the key that you specified.

```
import React from 'react';
import { connect } from 'react-redux';

import * as actions from '../store/actions.js';

class App extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <button onClick={this.props.initializeTheCart}>
        Start Shopping!
      </button>
    );
  }
}

const mapStateToProps = state => ({
  cart: state.cart,
});

const mapDispatchToProps = (dispatch, getState) => ({
  initializeTheCart: () => dispatch(actions.newCart()),
});

export default connect(
  mapStateToProps,
  mapDispatchToProps,
)(App);
```

- Before any of this can work, your entire application needs to be given access to the store. Your component (above) uses the redux `connect()` method to attach to the store, but without first “Providing” it to your application, that connection will fail. The provider wrapper is a means that React uses to allow child components to have access to higher level context.

```
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';

import './style.scss';

import App from './components/app';

import createStore from './store';
const store = createStore();

class Main extends React.Component {
  render() {
    return (
      <Provider store={store}>
        <React.Fragment>
          <App />
        </React.Fragment>
      </Provider>
    );
  }
}

const rootElement = document.getElementById('root');
ReactDOM.render(<Main />, rootElement);
```
