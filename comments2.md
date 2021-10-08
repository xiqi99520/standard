### 不要写日志注释

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	/**
	 * 2021-09-20: 创建结算方法 (王xx)
	 * 2021-09-21: 修改结算方法 (李xx)
	 * 2021-09-23: 删除结算方法 (陈xx)
	 * 2021-09-24: 合并代码 (admin)
	 */
	function combine(a, b) {
	  return a + b;
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	function combine(a, b) {
	  return a + b;
	}
```