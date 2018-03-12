# Night Mode Hack for Slack Desktop App

## You'll need to do this after each Slack update

Open either:

###Windows:

    C:\Users\Scellow\AppData\Local\slack\app-2.5.2\resources\app.asar.unpacked\src\static\index.js

###macOS:

    Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static/index.js

Then paste this at the end of the file:

```
// First make sure the wrapper app is loaded
document.addEventListener("DOMContentLoaded", function() { // eslint-disable-line
   // Then get its webviews
   let webviews = document.querySelectorAll(".TeamView webview");

   // Fetch our CSS in parallel ahead of time
   const cssURI = 'https://gist.githubusercontent.com/widget-/f97f6e6697b185692f3836e47e2b6ad3/raw/ea5b8764e66c44aa367f44dcff33f89c480ae58b/custom.css';
   let cssPromise = fetch(cssURI).then(response => response.text());

   // Then wait for the views to load
   webviews.forEach(webview => {
      webview.addEventListener('ipc-message', message => {
         if (message.channel == 'didFinishLoading')
            // Finally add the CSS in
            cssPromise.then(css => webview.insertCSS(css));
      });
   });
});
```

Restart Slack, and enjoy the dark theme

If you want to make your own theme, load the CSS you want, check the cssURI variable
