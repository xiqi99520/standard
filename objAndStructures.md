### 使用getters和setters

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function makeBankAccount() {
	  // ...
	
	  return {
	    balance: 0
	    // ...
	  };
	}
	
	const account = makeBankAccount();
	account.balance = 100;
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function makeBankAccount() {
	  // this one is private
	  let balance = 0;
	
	  // 一个"getter"，返回一个对象
	  function getBalance() {
	    return balance;
	  }
	
	  // 一个"setter"，返回一个对象
	  function setBalance(amount) {
	    // ... 在更新余额之前进行验证
	    balance = amount;
	  }
	
	  return {
	    // ...
	    getBalance,
	    setBalance
	  };
	}
	
	const account = makeBankAccount();
	account.setBalance(100);
```