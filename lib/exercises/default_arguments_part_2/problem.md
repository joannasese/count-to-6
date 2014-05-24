In JavaScript, unlike some other languages, default arguments can be expressions:

```js
function log(arg, transform = x => x) {
    console.log(transform(arg));
}

log("Hello");                       // "Hello"
log("Hello", y => y.toUpperCase()); // "HELLO"
```

In this example we used as our default transformation the identity function, `x => x`.

Default argument values can even depend on earlier arguments:

```js
function assertEquals5(val, error = `${val} does not equal 5!`) {
    assert.strictEqual(val, error);
}

assertEquals5(3); // "3 does not equal 5!"
```

---

For this exercise, you should write a function that will make a string really important, by adding a bunch of exclamation marks after it. The exact number of exclamation marks should be configurable, but by default, it should be equal to the length of the string. So:

```js
makeImportant("Hi", 5); // "Hi!!!!!"
makeImportant("Hi"); // "Hi!!"
makeImportant("Hello?", undefined); // "Hello?!!!!!!"
```

Bonus ES6 knowledge that might be helpful: ES6 includes a `String.prototype.repeat` that does exactly what you'd imagine.