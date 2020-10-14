## Routing

**Routing**

- Using `react-router`, you can easily toggle the visibility of componenets (or even pages) based on the URL/Route that the user engages with.

- `import {Route} from 'react-router-dom';`

- To use Browser Router properly, you eliminate your use of `<a>` tags and instead use its built-in `<Link>` component.

```
<Link to="/">Home</Link>
<Link to="/stuff">Stuff</Link>
```

- In practice, then, use the router componenet to look at either `/` or `/stuff` and based on that, displaying either the `Home` or the `List` component, like this:

```
 <Route exact path="/" component={Home} />
 <Route exact path="/stuff" render={() => <List>{items}</List>} />
