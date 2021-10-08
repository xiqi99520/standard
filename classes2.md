### 偏好组合而非继承

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class Employee {
	  constructor(name, email) {
	    this.name = name;
	    this.email = email;
	  }
	
	  // ...
	}
	
	class EmployeeTaxData extends Employee {
	  constructor(ssn, salary) {
	    super();
	    this.ssn = ssn;
	    this.salary = salary;
	  }
	
	  // ...
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class EmployeeTaxData {
	  constructor(ssn, salary) {
	    this.ssn = ssn;
	    this.salary = salary;
	  }
	
	  // ...
	}
	
	class Employee {
	  constructor(name, email) {
	    this.name = name;
	    this.email = email;
	  }
	
	  setTaxData(ssn, salary) {
	    this.taxData = new EmployeeTaxData(ssn, salary);
	  }
	  // ...
	}
```