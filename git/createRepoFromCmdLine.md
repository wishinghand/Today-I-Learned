## Replace USER with your username and REPO with your repository/application name!

`curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'`


```mkdir yourNewRepo && cd yourNewRepo```

```git init```

```git remote add origin https://github.com/USER/REPO.git```

```git add *```

```git commit -m "intial commit"```

```git push origin master```