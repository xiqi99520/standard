### 使用Object.assign设置默认对象

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const menuConfig = {
	  title: null,
	  body: "Bar",
	  buttonText: null,
	  cancellable: true
	};
	
	function createMenu(config) {
	  config.title = config.title || "Foo";
	  config.body = config.body || "Bar";
	  config.buttonText = config.buttonText || "Baz";
	  config.cancellable =
	    config.cancellable !== undefined ? config.cancellable : true;
	}
	
	createMenu(menuConfig);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const menuConfig = {
	  title: "Order",
	  // User did not include 'body' key
	  buttonText: "Send",
	  cancellable: true
	};
	
	function createMenu(config) {
	  let finalConfig = Object.assign(
	    {
	      title: "Foo",
	      body: "Bar",
	      buttonText: "Baz",
	      cancellable: true
	    },
	    config
	  );
	  return finalConfig
	  // config 现在等于: {title: "Order", body: "Bar", buttonText: "Send", cancellable: true}
	  // ...
	}
	
	createMenu(menuConfig);
```