### 使用默认实参而不是短路或条件

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function createMicrobrewery(name) {
	  const breweryName = name || "Hipster Brew Co.";
	  // ...
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function createMicrobrewery(name = "Hipster Brew Co.") {
	  // ...
	}
```