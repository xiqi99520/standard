### 不要写全局函数

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	Array.prototype.diff = function diff(comparisonArray) {
	  const hash = new Set(comparisonArray);
	  return this.filter(elem => !hash.has(elem));
	};
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class SuperArray extends Array {
	  diff(comparisonArray) {
	    const hash = new Set(comparisonArray);
	    return this.filter(elem => !hash.has(elem));
	  }
	}
```