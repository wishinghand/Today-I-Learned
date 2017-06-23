```
var elements = document.querySelectorAll("p"); // NodeList
var arrayElements = [].slice.call(elements); // Now the NodeList is an array

var arrayElements = Array.from(elements); // This is another way of converting NodeList to Array
```