### 函数应该做一件事

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function emailClients(clients) {
	  clients.forEach(client => {
	    const clientRecord = database.lookup(client);
	    if (clientRecord.isActive()) {
	      email(client);
	    }
	  });
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function emailActiveClients(clients) {
	  clients.filter(isActiveClient).forEach(email);
	}
	
	function isActiveClient(client) {
	  const clientRecord = database.lookup(client);
	  return clientRecord.isActive();
	}
```