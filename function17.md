### 删除无用代码

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function oldRequestModule(url) {
	  // ...
	}
	
	function newRequestModule(url) {
	  // ...
	}
	
	const req = newRequestModule;
	inventoryTracker("apples", req, "www.inventory-awesome.io");
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function newRequestModule(url) {
	  // ...
	}
	
	const req = newRequestModule;
	inventoryTracker("apples", req, "www.inventory-awesome.io");
```