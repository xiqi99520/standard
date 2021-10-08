### 避免副作用(下)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const addItemToCart = (cart, item) => {
	  cart.push({ item, date: Date.now() });
	};
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const addItemToCart = (cart, item) => {
	  return [...cart, { item, date: Date.now() }];
	};
```