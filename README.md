# node-es7-babel-template

Based on https://github.com/wahengchang/node-es7-babel-template/

It is an node.js used ES7 template, compiled by babel 

## Install

```
$ npm install babel-cli babel-preset-env --save-dev
```

## To Use
Modify start command, package.json
```javascript
 //./package.json
  ...

  "scripts": {
    "start": "babel-node --presets env app.js",
  },

  ...
```

Create a script with ES7 function, for example async/await
```javascript
 //./app.js

(async function() {
    var sleep = function(para) {
        return new Promise(function(resolve, reject) {
            setTimeout(function() {
                console.log('para: ', para)
                resolve(para * para)
            }, 1000)
        })
    }

    var result = await sleep(2);
    console.log('result: ', result);
}());
```

Run the script 
```
$ npm start

para:  2
result:  4

```