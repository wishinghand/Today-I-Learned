# Heroku basics

`heroku create app_name`

The above will add remotes if git initialized, if not do:
`git remote add heroku https://git.heroku.com/PROJECT_NAME.git`

`git push heroku master`

Open the app:
`heroku open`

Server side logs:
`heroku logs --tail`