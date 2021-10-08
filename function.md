### 函数参数(最好是2个或更少)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function createMenu(title, body, buttonText, cancellable) {
	  // ...
	}
	
	createMenu("Foo", "Bar", "Baz", true);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function createMenu({ title, body, buttonText, cancellable }) {
	  // ...
	}
	
	createMenu({
	  title: "Foo",
	  body: "Bar",
	  buttonText: "Baz",
	  cancellable: true
	});
```