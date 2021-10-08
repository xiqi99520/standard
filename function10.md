### 比起命令式编程，更支持函数式编程

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	const programmerOutput = [
	  {
	    name: "Uncle Bobby",
	    linesOfCode: 500
	  },
	  {
	    name: "Suzie Q",
	    linesOfCode: 1500
	  },
	  {
	    name: "Jimmy Gosling",
	    linesOfCode: 150
	  },
	  {
	    name: "Gracie Hopper",
	    linesOfCode: 1000
	  }
	];
	
	let totalOutput = 0;
	
	for (let i = 0; i < programmerOutput.length; i++) {
	  totalOutput += programmerOutput[i].linesOfCode;
	}
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	const programmerOutput = [
	  {
	    name: "Uncle Bobby",
	    linesOfCode: 500
	  },
	  {
	    name: "Suzie Q",
	    linesOfCode: 1500
	  },
	  {
	    name: "Jimmy Gosling",
	    linesOfCode: 150
	  },
	  {
	    name: "Gracie Hopper",
	    linesOfCode: 1000
	  }
	];
	
	const totalOutput = programmerOutput.reduce(
	  (totalLines, output) => totalLines + output.linesOfCode,
	  0
	);
```