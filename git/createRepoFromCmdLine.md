curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'

Remember replace USER with your username and REPO with your repository/application name!

```cd yourNewRepo```
```git init```
```git remote add origin https://github.com/USER/REPO.git```
```git add```
```git commit```
```git push origin master```