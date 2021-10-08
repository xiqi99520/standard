### 使用解释性变量

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const address = "One Infinite Loop, Cupertino 95014";
	const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
	saveCityZipCode(
	  address.match(cityZipCodeRegex)[1],
	  address.match(cityZipCodeRegex)[2]
	);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const address = "One Infinite Loop, Cupertino 95014";
	const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
	const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
	saveCityZipCode(city, zipCode);
```