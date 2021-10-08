### 函数名应该说明它们的作用

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function addToDate(date, month) {
	  // ...
	}
	
	const date = new Date();
	
	// 从函数名中很难看出添加了什么
	addToDate(date, 1);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function addMonthToDate(month, date) {
	  // ...
	}
	
	const date = new Date();
	addMonthToDate(1, date);
```