### 避免条件

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class Airplane {
	  // ...
	  getCruisingAltitude() {
	    switch (this.type) {
	      case "777":
	        return this.getMaxAltitude() - this.getPassengerCount();
	      case "Air Force One":
	        return this.getMaxAltitude();
	      case "Cessna":
	        return this.getMaxAltitude() - this.getFuelExpenditure();
	    }
	  }
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class Airplane {
	  // ...
	}
	
	class Boeing777 extends Airplane {
	  // ...
	  getCruisingAltitude() {
	    return this.getMaxAltitude() - this.getPassengerCount();
	  }
	}
	
	class AirForceOne extends Airplane {
	  // ...
	  getCruisingAltitude() {
	    return this.getMaxAltitude();
	  }
	}
	
	class Cessna extends Airplane {
	  // ...
	  getCruisingAltitude() {
	    return this.getMaxAltitude() - this.getFuelExpenditure();
	  }
	}
```