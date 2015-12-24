ES6
===

ReactJS

New Features/Changes
--------------------
* In-browser transform from JSX to JS and then to Virtual DOM. Then diffed to DOM.
* Build components using `var Component = React.createClass({ render: function() { ... } });`
* `render` *must* return a single node
* You can nest components in each other using markup
* React is uni-directional data flow. Models to components only
* How to render:

    ```
    React.render(<Component>, document.getElementById('container'));
    ```

* Dealing w/ state is done using `this.props`

    ```
    var Thing = React.createClass({
      getInitialState: function() {
        return {
          ingredient: 'Eggplant'
        };
      },
      render: function() {
        return (
          <div>
            <h2>{this.props.title}</h2>
            <h3>Ingredients: {this.state.ingredient}</h3>
          </div>
        );
      }
    });
    ...
    <Thing title="My Title!" />
    ```

* You can call arbitrary functions from within curly braces - best practice is to use methods that are declared at the class level
* Component state persists between renders
* You need to use `this.setState` to change a state value for it to persist between renders
* You can create elements in a list, but each needs a `key`, then you can do `this.props.data.map(function(data, index) { return <Thing key="index" ... /> });`
* For events, you can use `onClick` on a JSX component and then have that call a method name

Flux
----

