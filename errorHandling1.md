### 不要忽视被拒绝的promise

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	getdata()
	  .then(data => {
	    functionThatMightThrow(data);
	  })
	  .catch(error => {
	    console.log(error);
	  });
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	getdata()
	  .then(data => {
	    functionThatMightThrow(data);
	  })
	  .catch(error => {
	    // One option (more noisy than console.log):
	    console.error(error);
	    // Another option:
	    notifyUserOfError(error);
	    // Another option:
	    reportErrorToService(error);
	    // OR do all three!
	  });
```