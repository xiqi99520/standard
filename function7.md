### 避免副作用(上)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	//下面函数引用的全局变量
	//如果我们有另一个函数使用这个名字，现在它将是一个数组，它可能会破坏它。

	let name = "Ryan McDermott";
	
	function splitIntoFirstAndLastName() {
	  name = name.split(" ");
	}
	
	splitIntoFirstAndLastName();
	
	console.log(name); // ['Ryan', 'McDermott'];
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function splitIntoFirstAndLastName(name) {
	  return name.split(" ");
	}
	
	const name = "Ryan McDermott";
	const newName = splitIntoFirstAndLastName(name);
	
	console.log(name); // 'Ryan McDermott';
	console.log(newName); // ['Ryan', 'McDermott'];
```