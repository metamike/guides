ES6
===

EcmaScript 6 stuff

New Features/Changes
--------------------
* contains instead of indexOf
* Set()
* Object.assign()
* built-in promises

    ```
    var promise = new Promise(function(resolve, reject) {
      setTimeout(resolve, 1000);
    });

    promise.then(function() {
      console.log('1 second');
    });
    ```
