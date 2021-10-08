### 单一职责原则(SRP)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class UserSettings {
	  constructor(user) {
	    this.user = user;
	  }
	
	  changeSettings(settings) {
	    if (this.verifyCredentials()) {
	      // ...
	    }
	  }
	
	  verifyCredentials() {
	    // ...
	  }
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class UserAuth {
	  constructor(user) {
	    this.user = user;
	  }
	
	  verifyCredentials() {
	    // ...
	  }
	}
	
	class UserSettings {
	  constructor(user) {
	    this.user = user;
	    this.auth = new UserAuth(user);
	  }
	
	  changeSettings(settings) {
	    if (this.auth.verifyCredentials()) {
	      // ...
	    }
	  }
	}
```