# django-deployment-eng

Do stuff step by step!

# requirements installation


1) pip install gunicorn
2) pip install whitenoise


Description: 

Gunicorn helps your project work in server.

WhiteNoise helps your static files to work in server.


3) Create requirements.txt in your main directory (BASE_DIR).

4) pip freeze > requirements.txt


# Procfile


5) Create Procfile in your main directory (BASE_DIR).


Write it in your Procfile

6) web: gunicorn PATH_TO_WSGI.PY.wsgi


Warning:

Procfile has to be created without any type neither .txt nor .py.

Description: 

Your project will work via this wsgi file so in here we should say that our wsgi.py plays a role of worker.


# Heroku

First, you have to create a heroku account in Heroku.


Type this in terminal in order to log in to your heroku account.


7) heroku login

Warning:

While you type heroku login in terminal you should be in you account on Chrome, Edge, Browser.


After all, you can create a name for your project.

8) heroku create NAME OF YOUR PROJECT IN HEROKU.


Description:

It will be displayed in your account in heroku.

After you created project in terminal appears two links.
Save both of them, you will need them.


# .gitignore


9) You need to create .gitignore file without any type.

Description:

.gitignore file helps you to restrict the files or dirs from your directory to be deployed.


10)

virt
venv
env
.vscode
.idea
__pycharm__

Type these above in your .gitignore file.


Description:

These files will not be deployed and will not be added to git.
Heroku provides you all packages for your project according to your requirements.txt.


# static collection


11) python manage.py collectstatic

Type these in your terminal.


Description: 

By doing so, you collect all static files from not only your directory,
but static files of admin site into your BASE_DIR.


# settings.py


12) ALLOWED_HOSTS=['YOUR HOST']


In settings file in this field enter your host name.

Example:

Let's say that is your host name of project. 
https://django-project.herokuapp.com/

You are going to enter in this field your host without
https:// and / in the end, like django-project.herokuapp.com


13) MIDDLEWARE=[
    ...
    "whitenoise.middleware.WhiteNoiseMiddleware", 
    ...
]

Warning:

You have to enter these settings in second field of your MIDDLEWARE,
otherwise it is not going to work or triggers an error.


14) STATIC_ROOT = os.path.join(BASE_DIR / 'static')


# git


15) git init

Enter this in your terminal in order to create a git where all your project will be added in order to be deployed.


16) git add .

By doing this, you add all files to the git that ypu create earlier.


17) git commit -m 'initial'

Commit them so others when downloads sees this commit.


18) git push YOUR HEROKU GIT URL master

In place of YOUR HEROKU GIT URL enter your heroku account git url that you get it when you created project,
if you remember I told you to save it.

If you did not save it, go to your personal heroku account and choose the project that you created and go to settings,
there you see url that ends with .git .
Copy it and enter in place of YOUR HEROKU GIT URL.
