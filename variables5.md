### 不要添加不必要的上下文

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const Car = {
	  carMake: "Honda",
	  carModel: "Accord",
	  carColor: "Blue"
	};
	
	function paintCar(car, color) {
	  car.carColor = color;
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const Car = {
	  make: "Honda",
	  model: "Accord",
	  color: "Blue"
	};
	
	function paintCar(car, color) {
	  car.color = color;
	}
```