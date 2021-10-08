### Async/Await甚至比promise更清晰

#### Bad  ![logo](./images/icon_bad.svg ':size=WIDTHxHEIGHT')
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
#### Good  ![logo](./images/icon_good.svg ':size=WIDTHxHEIGHT')
```js
	import { get } from "request-promise";
	import { writeFile } from "fs-extra";
	
	async function getCleanCodeArticle() {
	  try {
	    const body = await get(
	      "https://en.wikipedia.org/wiki/Robert_Cecil_Martin"
	    );
	    await writeFile("article.html", body);
	    console.log("File written");
	  } catch (err) {
	    console.error(err);
	  }
	}
	
	getCleanCodeArticle()
```