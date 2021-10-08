### 只注释具有业务逻辑复杂性的东西

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	function hashIt(data) {
	  // 哈希值
	  let hash = 0;
	
	  // 字符串长度
	  const length = data.length;
	
	  // 循环遍历数据中的每个字符
	  for (let i = 0; i < length; i++) {
	    // 获取字符
	    const char = data.charCodeAt(i);
	    // 生成哈希值
	    hash = (hash << 5) - hash + char;
	    // 转换为32位整数
	    hash &= hash;
	  }
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function hashIt(data) {
	  let hash = 0;
	  const length = data.length;
	
	  for (let i = 0; i < length; i++) {
	    const char = data.charCodeAt(i);
	    hash = (hash << 5) - hash + char;
	
	    // 转换为32位整数
	    hash &= hash;
	  }
	}
```