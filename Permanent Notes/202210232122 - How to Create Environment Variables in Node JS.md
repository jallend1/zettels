**Related:** [[202210232112 - What Are Environment Variables in NodeJS]]

Create a file named simply ".env" in the root directory of the app. Conventions are that the variable names are in all capital letters, like:

```Node
PORT=4000
PATH=/home/data/images/
APIKEY=55555555

```

And these variables can be accessed inside the app

```JavaScript
console.log(process.env.PORT);
console.log(process.env.APIKEY);
```

If unable to access process.env from within the app, installing the dotenv package will remedy.


## References
---
[[202209271713 - ARTICLE - How to set up Environment Variable in Node JS]]