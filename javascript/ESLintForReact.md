# How to set up ESLint for React in Sublime Text

1. Uninstall all of your linters in Sublime Text that are about Javascript as well as the main SublimeLinter.
2. Run this command in the repo you want to lint: `npm install -D eslint eslint-plugin-react`.
   - Note: If you don't want to run that command every project, you can install them globally instead.
3. Reinstall the SublimeLinter package
4. Install the SublimeLinter-contrib-eslint package
5. In the top level of your repo that you want to be linted, run `eslint --init`. Follow the instructions and make sure you say "yes" to using JSX and React.
6. In the .eslintrc file that gets created, add these two rules at the end of your rules object: 
```
"react/jsx-uses-react": 1,
"react/jsx-uses-vars": 1
```
7. Restart Sublime Text