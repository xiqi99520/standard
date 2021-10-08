### 使用有意义且可读性高的变量名

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const yyyymmdstr = moment().format("YYYY/MM/DD");
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const currentDate = moment().format("YYYY/MM/DD");
```