### 更偏好ES2015/ES6类，而不是ES5普通函数

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const Animal = function(age) {
	  if (!(this instanceof Animal)) {
	    throw new Error("Instantiate Animal with `new`");
	  }
	
	  this.age = age;
	};
	
	Animal.prototype.move = function move() {};
	
	const Mammal = function(age, furColor) {
	  if (!(this instanceof Mammal)) {
	    throw new Error("Instantiate Mammal with `new`");
	  }
	
	  Animal.call(this, age);
	  this.furColor = furColor;
	};
	
	Mammal.prototype = Object.create(Animal.prototype);
	Mammal.prototype.constructor = Mammal;
	Mammal.prototype.liveBirth = function liveBirth() {};
	
	const Human = function(age, furColor, languageSpoken) {
	  if (!(this instanceof Human)) {
	    throw new Error("Instantiate Human with `new`");
	  }
	
	  Mammal.call(this, age, furColor);
	  this.languageSpoken = languageSpoken;
	};
	
	Human.prototype = Object.create(Mammal.prototype);
	Human.prototype.constructor = Human;
	Human.prototype.speak = function speak() {};
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class Animal {
	  constructor(age) {
	    this.age = age;
	  }
	
	  move() {
	    /* ... */
	  }
	}
	
	class Mammal extends Animal {
	  constructor(age, furColor) {
	    super(age);
	    this.furColor = furColor;
	  }
	
	  liveBirth() {
	    /* ... */
	  }
	}
	
	class Human extends Mammal {
	  constructor(age, furColor, languageSpoken) {
	    super(age, furColor);
	    this.languageSpoken = languageSpoken;
	  }
	
	  speak() {
	    /* ... */
	  }
	}
```