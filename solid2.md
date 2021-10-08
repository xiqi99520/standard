### 里氏替换原则(LSP)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class Rectangle {
	  constructor() {
	    this.width = 0;
	    this.height = 0;
	  }
	
	  setColor(color) {
	    // ...
	  }
	
	  render(area) {
	    // ...
	  }
	
	  setWidth(width) {
	    this.width = width;
	  }
	
	  setHeight(height) {
	    this.height = height;
	  }
	
	  getArea() {
	    return this.width * this.height;
	  }
	}
	
	class Square extends Rectangle {
	  setWidth(width) {
	    this.width = width;
	    this.height = width;
	  }
	
	  setHeight(height) {
	    this.width = height;
	    this.height = height;
	  }
	}
	
	function renderLargeRectangles(rectangles) {
	  rectangles.forEach(rectangle => {
	    rectangle.setWidth(4);
	    rectangle.setHeight(5);
	    const area = rectangle.getArea(); // BAD: Returns 25 for Square. Should be 20.
	    rectangle.render(area);
	  });
	}
	
	const rectangles = [new Rectangle(), new Rectangle(), new Square()];
	renderLargeRectangles(rectangles);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class Shape {
	  setColor(color) {
	    // ...
	  }
	
	  render(area) {
	    // ...
	  }
	}
	
	class Rectangle extends Shape {
	  constructor(width, height) {
	    super();
	    this.width = width;
	    this.height = height;
	  }
	
	  getArea() {
	    return this.width * this.height;
	  }
	}
	
	class Square extends Shape {
	  constructor(length) {
	    super();
	    this.length = length;
	  }
	
	  getArea() {
	    return this.length * this.length;
	  }
	}
	
	function renderLargeShapes(shapes) {
	  shapes.forEach(shape => {
	    const area = shape.getArea();
	    shape.render(area);
	  });
	}
	
	const shapes = [new Rectangle(4, 5), new Rectangle(4, 5), new Square(5)];
	renderLargeShapes(shapes);
```