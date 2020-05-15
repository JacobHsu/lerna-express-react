# lerna-express-react

`npm i lerna -g`  
`lerna init`

`cd packages`
`create-react-app front`

`cd packages`
`mkdir -p back/src`  
`cd back`  
`npm init --yes`
`yarn add express`

## Node SyntaxError

[SyntaxError: Cannot use import statement outside a module](https://stackoverflow.com/questions/58384179/syntaxerror-cannot-use-import-statement-outside-a-module)

2020 Update (Node 13.2.0+)

Add `"type": "module"` to the nearest parent package.json. With this, all .js and .mjs files are interpreted as ES modules.

To make Node treat your file as a ES module you [need to](https://nodejs.org/api/esm.html#esm_enabling)

* add "type": "module" to package.json
* add "--experimental-modules" flag to the node call

package.json

```js
  "type": "module",
  "scripts": {
    "build": "babel src -d build",
    "serve": "yarn build && yarn serve",
    "start": "node --experimental-modules build/index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```

## references

[lerna管理package](https://juejin.im/post/5d231eac6fb9a07ea33c398f)  
[Express+React Monorepo Setup with Lerna](https://benoithubert.net/2019/08/express-react-monorepo-setup-with-lerna.html)  
amaurymartiny/[login-with-metamask-demo](https://github.com/amaurymartiny/login-with-metamask-demo)
[讓我們先轉個 180 度：Node.js 與 npm](https://ithelp.ithome.com.tw/articles/10185974)