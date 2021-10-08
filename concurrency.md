### 使用promise，而不是回调

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
```js
	import { get } from "request";
	import { writeFile } from "fs";
	
	get(
	  "https://en.wikipedia.org/wiki/Robert_Cecil_Martin",
	  (requestErr, response, body) => {
	    if (requestErr) {
	      console.error(requestErr);
	    } else {
	      writeFile("article.html", body, writeErr => {
	        if (writeErr) {
	          console.error(writeErr);
	        } else {
	          console.log("File written");
	        }
	      });
	    }
	  }
	);
```
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	import { get } from "request-promise";
	import { writeFile } from "fs-extra";
	
	get("https://en.wikipedia.org/wiki/Robert_Cecil_Martin")
	  .then(body => {
	    return writeFile("article.html", body);
	  })
	  .then(() => {
	    console.log("File written");
	  })
	  .catch(err => {
	    console.error(err);
	  });
```