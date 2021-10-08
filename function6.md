### 不要使用标志作为函数参数

?>标志告诉您的用户，此功能不止一件事。 但功能应该做一件事。 如果它们根据布尔值遵循不同的代码路径，请分开您的功能。

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function createFile(name, temp) {
	  if (temp) {
	    fs.create(`./temp/${name}`);
	  } else {
	    fs.create(name);
	  }
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function createFile(name) {
	  fs.create(name);
	}
	
	function createTempFile(name) {
	  createFile(`./temp/${name}`);
	}
```