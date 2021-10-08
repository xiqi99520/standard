### 避免模糊映射

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const locations = ["Austin", "New York", "San Francisco"];
	locations.forEach(l => {
	  doStuff();
	  doSomeOtherStuff();
	  // ...
	  // ...
	  // ...
	  //  `l` 是什么意思?
	  dispatch(l);
	});
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const locations = ["Austin", "New York", "San Francisco"];
	locations.forEach(location => {
	  doStuff();
	  doSomeOtherStuff();
	  // ...
	  // ...
	  // ...
	  dispatch(location);
	});
```