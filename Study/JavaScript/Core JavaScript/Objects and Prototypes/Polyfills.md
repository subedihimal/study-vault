A **polyfill** is code that **adds missing modern JavaScript features to older browsers** that don’t support them.
```js
if (!Array.prototype.includes) {
  Array.prototype.includes = function (value) {
    for (let i = 0; i < this.length; i++) {
      if (this[i] === value) return true;
    }
    return false;
  };
}
```