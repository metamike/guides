ES6
===

EcmaScript 6 stuff

http://kangax.github.io/compat-table/es6/

New Features/Changes
--------------------
* `contains` instead of `indexOf`
* `Set()`
* `Object.assign()`
* built-in promises

    ```
    var promise = new Promise(function(resolve, reject) {
      setTimeout(resolve, 1000);
    });

    promise.then(function() {
      console.log('1 second');
    });
    ```
* Maps (like objects but without special properties)
* Use `let` to scope a variable to a block (otherwise you just have global or function scope)
* Array comprehensions (like python)

    ```
    var arr = [1, 2, 3, 4];
    var doubled = [for (x of arr) 2*x];
    ```
* Fat arrow
* Destructuring assignment for assigning names to function parameters

    ```
    var arr = [1, 2, 3];
    func(arr);
    function func([fst, snd, thd]) {
      alert(fst);
      ...
    }
    function dealWithRest(...args) {
      var [options, callback] = args;   // more destructuring
      alert(options.v);
    }
    ```
* Template strings using backticks and `${}`
* Multiline string support
* Generators

    ```
    function* inf() {
      var i = 0;
      while(true) { yield ++i; }
    }
    for(var x of inf()) {
      alert(x);
      if (x > 3) { break; }
    }
    ```
* `class` syntax is just syntactic sugar
* Module system

    ```
    // a.js
    var name = 'some name';
    export default name;

    // b.js
    import name from 'a';
    alert(name);

    // importing names using a namespace
    import * as a from 'a';
    a.name;
    a.location; // etc
    ```

