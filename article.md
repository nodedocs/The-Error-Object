# The Error Object

The error object is a built-in object that provides a standard set of useful information when an error occurs, such as a stack trace and the error message. For example:

Code:

    var error = new Error("The error message");
    console.log(error);
    console.log(error.stack);

Result:


    { stack: [Getter/Setter],
      arguments: undefined,
      type: undefined,
      message: 'The error message' }
    Error: The error message
        at Object.<anonymous> (/home/nico/example.js:1:75)
        at Module._compile (module.js:407:26)
        at Object..js (module.js:413:10)
        at Module.load (module.js:339:31)
        at Function._load (module.js:298:12)
        at Array.0 (module.js:426:10)
        at EventEmitter._tickCallback (node.js:126:26)

The `error.stack` property value shows you where an error came from, as well as a list of the function calls that preceded it - for your convenience, `error.stack` always prints `error.message` as the first line of its output, making `error.stack` a convenient single property to log during debugging.

If you want to add more information to the Error object, you can always add some custom properties, just as with any other Javascript object: 

    var error = new Error("The error message");
    error.http_code = 404;
    console.log(error);

For more details how to use the Error object, check out the [article on error conventions](/what-are-the-error-conventions)
