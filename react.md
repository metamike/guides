ReactJS
=======

ReactJS - build web stuff

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
* When hitting a route, a component is rendered (and all its parents)
* To start the router:

    ```
    var routes = (
      <Route name="RecipeBook" path="/" handler={ComponentName}>
        <DefaultRoute handler={Component} />
        <Route name="recipeDetails" path="/recipeDetails/:_id" handler={Component} />
        ...
      </Route>
    );
    Router.run(routes, function (handler, state) {
      var params = state.params;
      React.render(<Handler params={params} data={data} />,
        document.getElementById('container'));
    });
    /* Then in the component itself: */
    <RouteHandler {...this.props} />
    ```

* When there's no path specified, it just uses `name`

Flux
----
Flux: "A bunch of callbacks w/ some organization and a subscription pattern"

* Primary Flow: user interacts with some component, an action is fired with the data, one or more stores are subscribed to the change and update, then they emit changes which updates the subscribed new components with new props
* Using McFly, can create actions like this:

    ```
    var Actions = Flux.createActions({action: function(text) { return { ... }; }});
    ```

* The store is important in Flux:

    ```
    var _array = [];
    var Store = Flux.createStore({
      getRecipes: function() { return _info; }
    }, function(payload) {
      if (payload.actionType === 'ADD') {
        _array.push(payload.text);
        Store.emitChange();
      }
    });
    ```

* To wire in Flux and the store

    ```
    var Component = React.createClass({
      mixins: [Store.mixin],
      render: ...
    });
    ```

Folder Layout
-------------
* Try this:

    ```
    components/
    router
    ```
