### 避免类型检查(下)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function combine(val1, val2) {
	  if (
	    (typeof val1 === "number" && typeof val2 === "number") ||
	    (typeof val1 === "string" && typeof val2 === "string")
	  ) {
	    return val1 + val2;
	  }
	
	  throw new Error("Must be of type String or Number");
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function combine(val1, val2) {
	  return val1 + val2;
	}
```