### 不要过度优化

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	// 在旧浏览器上，每次使用未缓存的 `list.length` 迭代都会代价高昂
	// 因为`list.length` 重新计算。 在现代浏览器中，这是优化的。
	for (let i = 0, len = list.length; i < len; i++) {
	  // ...
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	for (let i = 0; i < list.length; i++) {
	  // ...
	}
```