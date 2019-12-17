###### Partial Application: https://www.freecodecamp.org/news/how-to-use-partial-application-to-improve-your-javascript-code-5af9ad877833/

###### Bind Polyfill

```
Function.prototype.bind2 = function(ctx, bindArgs) {
  let fn = this;
  return function(...callArgs) {
    fn.apply(ctx, [...bindArgs, ...callArgs]);
  };
};

const a = {
  a: "a",
  b: "b"
};

const fn = function(c, d) {
  console.log(this.a, this.b, c, d);
};

const fn2 = fn.bind2(a, "c");

fn2("d");
```
