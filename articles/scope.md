## Scoping

- Scope determines the visibility or accessibility of a variable or other resource in the area of your code.

### Global scope

- Only one global scope in the JavaScript document. It's the area outside of all functions. The variables defined inside the global scope can be accessed and altered in any other scopes.

```javascript
//global scope
var fruit = "apple";
console.log(fruit); //apple

function getFruit() {
  console.log(fruit); //fruit is accessible here
}

getFruit(); //apple
```

### Local scope

- Variables declared inside the functions become Local to the function and are considered in the corresponding local scope. Every Functions has its own scope.
- Local scope can be divided into **function scope** and **block scope**.

```javascript
//global scope
function foo1() {
  //local scope 1
  function foo2() {
    //local scope 2
  }
}

//global scope
function foo3() {
  //local scope 3
}

//global scope
```

### Function scope

- Whenever you declare a variable in a function, the variable is visible only within the function. You can't access it outside the function.
- **var** is the keyword to define variable for a function-scope accessibility.

```javascript
function foo() {
  var fruit = "apple";
  console.log("inside function: ", fruit);
}

foo(); //inside function: apple
console.log(fruit); //error: fruit is not defined
```

### Block scope (introduced in es6)

- Everything inside a **{curly brackets}** is a block-scope
- **const** and **let** keywords allow developers to declare variables in the block scope, which means those variables exist only within the corresponding block

```javascript
function foo() {
  if (true) {
    var fruit1 = "apple"; //exist in function scope
    const fruit2 = "banana"; //exist in block scope
    let fruit3 = "strawberry"; //exist in block scope
  }
  console.log(fruit1);
  console.log(fruit2);
  console.log(fruit3);
}

foo();
//result:
//apple
//error: fruit2 is not defined
//error: fruit3 is not defined
```

### Lexical scope

- Lexical scope means the children scope have the access to the variables defined in the parent scope. The children functions are lexically bound to the execution context of their parents.

```javascript
function foo1() {
  var fruit1 = "apple";
  const fruit2 = "banana";
  let fruit3 = "strawberry";
  function foo2() {
    console.log(fruit1);
    console.log(fruit2);
    console.log(fruit3);
  }
  foo2();
}

foo1();

//result:
//apple
//banana
//strawberry
```
