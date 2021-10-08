### 接口分离原则(ISP)

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	class DOMTraverser {
	  constructor(settings) {
	    this.settings = settings;
	    this.setup();
	  }
	
	  setup() {
	    this.rootNode = this.settings.rootNode;
	    this.settings.animationModule.setup();
	  }
	
	  traverse() {
	    // ...
	  }
	}
	
	const $ = new DOMTraverser({
	  rootNode: document.getElementsByTagName("body"),
	  animationModule() {} // 大多数时候，我们不需要在遍历时使用动画
	  // ...
	});
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	class DOMTraverser {
	  constructor(settings) {
	    this.settings = settings;
	    this.options = settings.options;
	    this.setup();
	  }
	
	  setup() {
	    this.rootNode = this.settings.rootNode;
	    this.setupOptions();
	  }
	
	  setupOptions() {
	    if (this.options.animationModule) {
	      // ...
	    }
	  }
	
	  traverse() {
	    // ...
	  }
	}
	
	const $ = new DOMTraverser({
	  rootNode: document.getElementsByTagName("body"),
	  options: {
	    animationModule() {}
	  }
	});
```