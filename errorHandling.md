### 不要忽视捕获错误

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	try {
	  functionThatMightThrow();
	} catch (error) {
	  console.log(error);
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	try {
	  functionThatMightThrow();
	} catch (error) {
	  // One option (more noisy than console.log):
	  console.error(error);
	  // Another option:
	  notifyUserOfError(error);
	  // Another option:
	  reportErrorToService(error);
	  // OR do all three!
	}
```