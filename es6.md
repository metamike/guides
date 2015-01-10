ES6
===

EcmaScript 6 stuff

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
