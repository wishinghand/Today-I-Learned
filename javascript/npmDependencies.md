If you need an NPM module to work in your directory but not saved to `package.json`, then run:
```
npm install gulp
```

If you want a module to run when deployed, save it to dependencies:
```
npm install vue --save
```

If you want a module to only run while developing but not be deployed:
```
npm install webpack --save-dev
```