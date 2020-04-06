## var, let and const

|                              |      var       |     let     |    const    |
| ---------------------------- | :------------: | :---------: | :---------: |
| reassigned                   |       O        |      O      |      X      |
| Scope                        | Function scope | Block scope | Block scope |
| Reference before declaration |       O        |      X      |      X      |

### var

- Old way to declare variable in javaScript
- Var is function-scoped

```javascript
var foo = "outside";
var fooFunction = function () {
  var foo = "inside";
};
fooFunction();
console.log(foo); //print outside
```

```javascript
var foo = "outside";
if (true) {
  var foo = "inside";
  console.log(foo); //print inside
}
console.log(foo); //print inside
```

```javascript
var a = [1, 2, 3];

for (var i = 0; i < a.length; i++) {
  let x = a[i];
  console.log(x);
}
console.log(i);

//result:
//1
//2
//3

//3
```

### let

- Variables that can be re-assigned.
- let is block-scoped

```javascript
let foo = "outside";
if (true) {
  let foo = "inside";
  console.log(foo); //print inside
}
console.log(foo); //print outside
```

### const

- Variables that can't be re-assigned.
- If it's an object, properties of the object can still change.

```javascript
const PI = 3.141593;
```

```javascript
const object = { foo: "a", bar: "b" };
object.foo = "foo";
```
