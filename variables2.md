### 使用可搜索的名称

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	// 86400000是代表什么?
	setTimeout(blastOff, 86400000);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	// 将它们声明为大写的命名常量
	const MILLISECONDS_PER_DAY = 60 * 60 * 24 *  1000; //86400000;
	
	setTimeout(blastOff, MILLISECONDS_PER_DAY);
```