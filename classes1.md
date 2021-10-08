### 使用方法链接

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class Car {
	  constructor(make, model, color) {
	    this.make = make;
	    this.model = model;
	    this.color = color;
	  }
	
	  setMake(make) {
	    this.make = make;
	  }
	
	  setModel(model) {
	    this.model = model;
	  }
	
	  setColor(color) {
	    this.color = color;
	  }
	
	  save() {
	    console.log(this.make, this.model, this.color);
	  }
	}
	
	const car = new Car("Ford", "F-150", "red");
	car.setColor("pink");
	car.save();
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class Car {
	  constructor(make, model, color) {
	    this.make = make;
	    this.model = model;
	    this.color = color;
	  }
	
	  setMake(make) {
	    this.make = make;
	    // 注意:返回这个用于链接
	    return this;
	  }
	
	  setModel(model) {
	    this.model = model;
	    // 注意:返回这个用于链接
	    return this;
	  }
	
	  setColor(color) {
	    this.color = color;
	    // 注意:返回这个用于链接
	    return this;
	  }
	
	  save() {
	    console.log(this.make, this.model, this.color);
	    // 注意:返回这个用于链接
	    return this;
	  }
	}
	
	const car = new Car("Ford", "F-150", "red").setColor("pink").save();
```