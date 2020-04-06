## Arrow function

- **=>** Are anonymous
- Make our code more concise, and simplify function scoping and the this keyword
- By using arrow functions, we avoid having to type the function keyword, return keyword (it’s implicit in arrow functions), and curly brackets.

```javascript
const multiplyES6 = (x, y) => x * y;
```

- In case there is only one parameter, can avoid brackets

```javascript
const phraseSplitterEs6 = (phrase) => phrase.split(" ");
```

- Arrow functions, like function expressions, can be used to return an object literal expression. The only caveat is that the body needs to be wrapped in parentheses, in order to distinguish between a block and an object (both of which use curly brackets).

```javascript
var setNameIdsEs6 = (id, name) => ({ id: id, name: name });
```
