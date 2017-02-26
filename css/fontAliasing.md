# Enabling Font Aliasing

These CSS settings will make fonts look better on desktop, it doesn't work on mobile because they don't support subpixel rendering.

Webkit default:
`-webkit-font-smoothing: subpixel-antialiased;`

Smoother fonts
`-webkit-font-smoothing: antialiased;`

use it like:
```
html{
    -webkit-font-smoothing: antialiased;
}
```