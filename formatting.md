### 使用一致的大小写

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const DAYS_IN_WEEK = 7;
	const daysInMonth = 30;
	
	const songs = ["Back In Black", "Stairway to Heaven", "Hey Jude"];
	const Artists = ["ACDC", "Led Zeppelin", "The Beatles"];
	
	function eraseDatabase() {}
	function restore_database() {}
	
	class animal {}
	class Alpaca {}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const DAYS_IN_WEEK = 7;
	const DAYS_IN_MONTH = 30;
	
	const SONGS = ["Back In Black", "Stairway to Heaven", "Hey Jude"];
	const ARTISTS = ["ACDC", "Led Zeppelin", "The Beatles"];
	
	function eraseDatabase() {}
	function restoreDatabase() {}
	
	class Animal {}
	class Alpaca {}
```