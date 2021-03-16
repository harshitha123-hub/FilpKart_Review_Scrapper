# FilpKart_Review_Scrapper

**App Deployed link : https://salty-fjord-86094.herokuapp.com/**

Flask_app.py is created to run on local machine,we need to have a mongoDB database connection to run this code.

app.py is created for deployment purpose.


1.	Steps before cloud deployment:
We need to change our code a bit so that it works unhindered on the cloud, as well.

a)	Add a file called ‘gitignore’ inside the ‘reviewScrapper’ folder. This folder contains the list of the files which we don’t want to include in the git repository.

b)	Add a file called ‘Procfile’ inside the ‘reviewScrapper’ folder. This folder contains the command to run the flask application once deployed on the server: 
    web: gunicorn app:app

c)	Open a command prompt window and navigate to your ‘reviewScrapper’ folder. Enter the command ‘pip freeze > requirements.txt’. This command generates the ‘requirements.txt’ file. My requirements.txt looks like:

    beautifulsoup4==4.8.1
    bs4==0.0.1
    certifi==2019.9.11
    Click==7.0
    Flask==1.1.1
    Flask-Cors==3.0.8
    gunicorn==20.0.4
    itsdangerous==1.1.0
    Jinja2==2.10.3
    MarkupSafe==1.1.1
    numpy==1.17.4
    opencv-python==4.1.2.30
    Pillow==6.2.1
    pymongo==3.9.0
    requests==2.21.0
    requests-oauthlib==1.2.0
    six==1.13.0
    soupsieve==1.9.5
    Werkzeug==0.16.0

requirements.txt helps the Heroku cloud app to install all the dependencies before starting the webserver.

3. Heroku app creation and deployment

a.	After installing the Heroku CLI, Open a command prompt window and navigate to your ‘reviewScrapper’ folder.

b.	Type the command ‘heroku login’ to login to your heroku account as shown   below:
 
c.	After logging in to Heroku, enter the command ‘heroku create’ to create a heroku app. It will give you the URL of your Heroku app after successful creation.

d.	Before deploying the code to the Heroku cloud, we need to commit the changes to the local git repository.

e.	Type the command ‘git init to initialize a local git repository  as shown below:
 
f.	Enter the command ‘git status’ to see the uncommitted changes

g.	Enter the command ‘git add .’ to add the uncommitted changes to the local repository.

i.	Enter the command ‘git commit -am "make it better"’ to commit the changes to the local repository.

j.	Enter the command ‘git push heroku master’ to push the code to the heroku cloud.

k.	After deployment, heroku gives you the URL to hit the web API.

l.	Once your application is deployed successfully, enter the command ‘heroku logs --tail’ to see the logs.
