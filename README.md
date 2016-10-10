# reactProgrammingPatterns

Our programming pattern uses two React components: a stateful component, and a stateless component. "Stateful" describes any component that has a getInitialState function; "stateless" describes any component that does not.

In our pattern, a stateful component passes its state down to a stateless component.
___________________________________________________

How does a component change its props?

The answer: it doesn't!

A component should never update this.props. Look below to see an example of what not to do.

This is potentially confusing. props and state store dynamic information. Dynamic information can change, by definition. If a component can't change its props, then what are props for?

A React component should use props to store information that can be changed, but can only be changed by a different component.

A React component should use state to store information that the component itself can change.

```js
var React = require('react');

var Bad = React.createClass({
  render: function () {
    this.props.message = 'yo'; // NOOOOOOOOOOOOOO!!!
    return <h1>{this.props.message}</h1>;
  }
});
```
