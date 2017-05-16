# View Commits Not Yet Pushed Upstream

This command shows a full log and compares it with the given branch (master in this example):

```
git log origin/master..HEAD
```


This command shows a shorter view of unpushed commits:
```git cherry -v```