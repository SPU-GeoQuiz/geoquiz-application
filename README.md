# Geoquiz


## ABOUT
This project is originally developed for a political science professor to use for her teaching at SPU and is supported by ETM (Educational Technogloy and Media). 

The project contains codes for quiz and front end for managing database.
![image](/images/quiz-demo.gif)


## Before Running the application

* Clone Repository to your machine
```
$ git clone "GIT REPOSITORY"
```
* Go to the repository and install npm to install all the dependencies.

```
$ npm install
```

## Initializing the database

There are two data files: for countries and users. 
countryDatabase.json stores information about countries of the world for the quiz, and userDatabase.json stores user information for accessing database page. 

Before running the application, make sure to create database using
```
$ node createdatabase.js
```

## Running the application

After installing npm and initializing the database, the command below will start the application.

```
$ node app.js
```
You should see the messages if the application starts running successfully.

![image](/images/nodeMessage.png)

In order to run the application permanently, install pm2 using
```
$ npm install pm2 -g 
```
Then use below command to run the application.
```
pm2 start app.js
```

## Front end for the database

When the app starts for the first time (/login), there is default credentials for admin. 
Use id: etm and password: geoquiz2018 to access the page then add a new user. Make sure user name is admin to grant access to manage user page. If you don't want user to have access to manage user page, simply change user name to something else.
You can remove the default credentials afterwards. 

![image](/images/database-demo.gif "Database Demo")


## Canvas Integration 

First the application needs to be added as an application to Canvas. It also requires a token to send the grade back to Canvas, so the user must generate a token and make sure that it has permission to post grades. For more infomation on how to generate a token, visit https://community.canvaslms.com/docs/DOC-10806-4214724194
The acquired token can be saved in .env file 

```
TOKEN = ...
```
and make sure to uncomment the top of the country.routes.js file 

![image](/images/token.png)

Then you can uncomment the sections router.post('/submission') and router.post('/quizStarted') in the file country.router.js. 
Make sure to change the url to your school's canvas page. 

![image](/images/url.png)
