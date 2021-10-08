### 依赖反转原则(DIP)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class InventoryRequester {
	  constructor() {
	    this.REQ_METHODS = ["HTTP"];
	  }
	
	  requestItem(item) {
	    // ...
	  }
	}
	
	class InventoryTracker {
	  constructor(items) {
	    this.items = items;
	
	    // BAD：我们创建了对特定请求实现的依赖项。
     	    // 我们应该只使用requestitems依赖于请求方法:' request '
	    this.requester = new InventoryRequester();
	  }
	
	  requestItems() {
	    this.items.forEach(item => {
	      this.requester.requestItem(item);
	    });
	  }
	}
	
	const inventoryTracker = new InventoryTracker(["apples", "bananas"]);
	inventoryTracker.requestItems();
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class InventoryTracker {
	  constructor(items, requester) {
	    this.items = items;
	    this.requester = requester;
	  }
	
	  requestItems() {
	    this.items.forEach(item => {
	      this.requester.requestItem(item);
	    });
	  }
	}
	
	class InventoryRequesterV1 {
	  constructor() {
	    this.REQ_METHODS = ["HTTP"];
	  }
	
	  requestItem(item) {
	    // ...
	  }
	}
	
	class InventoryRequesterV2 {
	  constructor() {
	    this.REQ_METHODS = ["WS"];
	  }
	
	  requestItem(item) {
	    // ...
	  }
	}
	
	//通过在外部构造依赖并注入它们，我们可以很容易地实现
	//将我们的request模块替换为一个使用WebSockets的新模块。
	const inventoryTracker = new InventoryTracker(
	  ["apples", "bananas"],
	  new InventoryRequesterV2()
	);
	inventoryTracker.requestItems();
```