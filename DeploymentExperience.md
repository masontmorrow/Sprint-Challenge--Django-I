The deployment was unsuccessful because of the `collectstatic` command run during pushing to Heroku. Solutions provided in the Heroku documentation did not work, nor did `whitenoise`. I thought perhaps it was a Python version issue, because I had changed from version 3.7 to 3.6.6 in my pipenv, but after removing that environment and creating a new one, the error now reads `FileNotFoundError: [Errno 2] No such file or directory: '/tmp/build_42d2dbfb70fc68bb7dad9713603a5f4e/static'`. 

Heroku suggests you can turn off the `collectstatic` command during a push, but it seems as if `whitenoise` is not configured properly and I have not found a solution yet.

### Update

After struggling with the `collectstatic` command during `git push heroku master`, I disabled the command to allow for uploading. I had to run this command locally before pushing to add CSS styling to the app, because running the command with the heroku cli would not update the application, even after clearing the application cache. 