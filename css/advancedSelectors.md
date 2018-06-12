# The Less-Than-Obvious Selectors in CSS

Descendent: Select all of `B` recursively inside of `A`

```
A B {
    // CSS rules go here
}
```

List: Selects elements in a comma separated list
```
A, B {
    // CSS rules go here
}
```

Universal Descendents: Selects Everything inside of `A`
```
A * {
    // CSS rules go here
}
```

Adjacent Sibling: Select an element that directly follows another
```
A + B {
    // CSS rules go here
}
```

Adjacent Sibling: Select elements that directly follows another
```
A ~ B {
    // CSS rules go here
}
```

Child: Select all of `B` that is a direct child of `A`
```
A > B {
    // CSS rules go here
}
```
