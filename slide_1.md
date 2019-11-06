# Async Await

- ### Lets code

### Basic Example

> The word “async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.
> ```javascript
> async function f() {
>  return 1;
> }

> f().then(alert); // 1
> ```
