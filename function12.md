### 避免负面条件

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function isDOMNodeNotPresent(node) {
	  // ...
	}
	
	if (!isDOMNodeNotPresent(node)) {
	  // ...
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function isDOMNodePresent(node) {
	  // ...
	}
	
	if (isDOMNodePresent(node)) {
	  // ...
	}
```