# Questions

1. Get the Values of the given object.

```js
let x = {
  a: 1,
  b: 2
};

//Solution 1
let objectValues = Object.values(x);
console.log(objectValues);

//Solution 2
let objectValues = [];
for (val in x) {
  objectValues.push(x[val]);
}
console.log(objectValues);
```

2. Convert x to y

```js
let x = "hi";

let y = "ih";

//Solution
const reverseString = str =>
  str
    .split("")
    .reverse()
    .join("");

console.log(reverseString(x));
```

3. Modify the Object obj such that obj.getA().getB() prints both the console logs.

```js
//obj.getA().getB() should print both the console.logs
const obj = {
  a: 1,
  b: 2,
  getA() {
    console.log(this.a);
  },
  getB() {
    console.log(this.b);
  }
};

//Solution
const obj = {
  a: 1,
  b: 2,
  getA() {
    console.log(this.a);
    return this;
  },
  getB() {
    console.log(this.b);
  }
};
```

4. [1, 2].print(); // 1, 2

```js
//Solution
Array.prototype.print = function() {
  console.log(this.join(","));
};
```

5. Captitalize first letter of Each word in a String

```js
//example: joHN dOe => John Doe

//Solution 1
let name = "joHN dOe";

name
  .split(" ")
  .map(ele => ele[0].toUpperCase() + ele.substr(1).toLowerCase())
  .join(" ");

//Solution 2
String.prototype.capitalizeFirst = function() {
  console.log(
    this.split(" ")
      .map(ele => ele[0].toUpperCase() + ele.substr(1).toLowerCase())
      .join(" ")
  );
};
name.capitalizeFirst();
```

6. What is the difference between keywords 'let' and 'var' ?

1) **var** has been in the JavaScript since the beginning. **let** was introduced in es6.

2) **let** is block scoped and **var** is function scoped. So variables declared with **var** keyword are garbage collected at the end of the function whereas **let** variables cease to exist after the block it is defined in.

3) **var** declarations are hoisted with **undefined** value and **let** variables are hoisted but remain **uninitialized**. It gives reference error in its **temporal dead zone** (TDZ).

```js
//Block Vs Function scoping
let x = function() {
  if (true) {
    var v = 2; //remains in existence till the function x
    let l = 1; //remains in existence only till enclosing block
  }

  console.log(v); //2
  console.log(l); //reference error
};
x();

//Hoisting of let Vs var
let x = function() {
  if (true) {
    console.log(v); //undefined
    console.log(l); //reference error

    var v = 2; //variables with 'var'  keyword are hoisted to the top of the function
    let l = 1; // 'let' variables are hoisted but will give reference error in TDZ.
  }
};
x();
```

7. Difference between '==' and '===' operators.

'==' is an **equality** operator and '===' is an **identity** operator. As the name suggests, the equality operator will make the data type the same before making a comparison also known as type coercion. The identity or strict equality operator checks for the value as well as data type to be same for the comparison to be equal.

```js
//equality operator

1 == 1; // true
"1" == 1; // true
1 == "1"; // true
0 == false; // true
0 == null; // false
var object1 = { key: "value" },
  object2 = { key: "value" };
object1.key == object2.key; //true
0 == undefined; // false
null == undefined; // true

// identity operator

3 === 3; // true
3 === "3"; // false
var object1 = { key: "value" },
  object2 = { key: "value" };
object1 === object2; //false
```
