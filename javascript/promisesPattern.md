I *think* this is how it goes:
The triggering function (`findSomething()`) needs to return a promise. Then each return object needs to be called as the argument to then next function.
```
findSomething()
  .then((something) => transformSomething(something))
  .then((transformed) => validateTransformed(transformed))
  .then((validated) => console.log('data is valid:', validated)
  .catch((error) => console.error(new Error(error))
```