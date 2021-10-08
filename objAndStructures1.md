### 使对象具有私有成员

?> 这可以通过闭包(针对ES5及以下版本)来实现

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const Employee = function(name) {
	  this.name = name;
	};
	
	Employee.prototype.getName = function getName() {
	  return this.name;
	};
	
	const employee = new Employee("John Doe");
	console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
	delete employee.name;
	console.log(`Employee name: ${employee.getName()}`); // Employee name: undefined
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function makeEmployee(name) {
	  return {
	    getName() {
	      return name;
	    }
	  };
	}
	
	const employee = makeEmployee("John Doe");
	console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
	delete employee.name;
	console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
```