make a new branch and switch to it in one command:
`git checkout -b name_of_new_branch`

commit all changed files in staging area (the `-a` has to come first):
`git commit -a -m "message for commit"`

get new branch onto origin:
`git push origin new_branch_name`

set new remote:
`git remote add remote_name http://remote_path.com/.git`