### 封装条件

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	if (fsm.state === "fetching" && isEmpty(listNode)) {
	  // ...
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function shouldShowSpinner(fsm, listNode) {
	  return fsm.state === "fetching" && isEmpty(listNode);
	}
	
	if (shouldShowSpinner(fsmInstance, listNodeInstance)) {
	  // ...
	}
```