# Easy Sticky Footer

Make sure you have a `<main>` element in your `<body>` or else it won't work.

```
body {
    display: flex;
    min-height: 100vh;
    flex-direction: column;
  }

  main {
    flex: 1 0 auto;
  }
```