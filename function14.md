### 避免类型检查(上)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function travelToTexas(vehicle) {
	  if (vehicle instanceof Bicycle) {
	    vehicle.pedal(this.currentLocation, new Location("texas"));
	  } else if (vehicle instanceof Car) {
	    vehicle.drive(this.currentLocation, new Location("texas"));
	  }
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function travelToTexas(vehicle) {
	  vehicle.move(this.currentLocation, new Location("texas"));
	}
```