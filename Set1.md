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
