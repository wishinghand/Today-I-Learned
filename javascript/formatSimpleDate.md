```
var d = new Date();
var displayDate = (d.getMonth() + 1) + '/' + d.getDate() + '/' + d.getFullYear();

// Template String version
var displayDate = `${(d.getMonth() + 1)}/${d.getDate()}/${d.getFullYear()}`;
```

`new Date();` gets you `Thu Mar 30 2017 11:16:02 GMT-0700 (PDT)`

The rest of the code will output: `3/30/2017`