# Reverse Engineering Code
[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://www.mit.edu/~amini/LICENSE.md)
<br>

 Reverse engineering code that allows users to log in and out of an app and creates a unique session. It uses a MySQL database to store data and a password encrypter to keep user data safe. To learn more check out the table of contents below.

<br>
<br> 
<hr>

## Table of Contents:
* [Dependencies](#Dependencies)
* [Installation](#Installation)
* [Code Explained](#Code-Explained)
    * [server.js](#server.js)
    * [config](#config)
    * [models](#models)
    * [routes](#routes)
    * [public](#public)

<br>

<hr>
<br>
<br>

## Dependencies
* [Express](https://www.npmjs.com/package/express)
* [Express-Session](https://www.npmjs.com/package/express-session)
* [Bcrypt](https://www.npmjs.com/package/bcrypt)
* [MySQL2](https://www.npmjs.com/package/mysql2)
* [Passport](https://www.npmjs.com/package/passport)
* [Passport-Local](https://www.npmjs.com/package/passport-local)
* [Sequelize](https://www.npmjs.com/package/sequelize)


<br>
<br>
<br>

## Installation
All dependencies are ready in the package.json file in the root directory.
To install dependencies run:
```
npm install
```
To run locally with node:
```
node server.js
```
It should run through express or locally on localhost through port 8080 :
```javaScript
var PORT = process.env.PORT || 8080;
```
Create a new database on MySQL called "passport_demo".
```
CREATE DATABASE IF NOT EXISTS passport_demo;
```

<br>
<br>
<br>
<hr>
<br>

# Code Explained
## server.js
* The server.js file is where we grab our required packages and set up our server. It is where everything is brought together. We create our "db" variable and import our models to setup how our database will handle info. This file also imports our html routes and api routes. The express, express-session, and passport variables are established to be use for server functionality. We establish which port should be used. We also configure Express to parse data, use the static folder, create express sessions per user login, and sync our database. 

<br>
<br>
<br>
<hr>


## config
<br>

### config.json
* Contains an object listing our database information. Includes details like database name and password. The "development" object contains info for the server we use during app development. The production object contains the details for our deployed app's server. If developers choose to use databases such as JAWSDB or others this is where they fill in the info pertaining to their database for the final product. With JAWSDB for example we would include the key value pair "use_env_variable: JAWSDB_URL" in place of username and password to keep our server info secure.

```json
{
  "development": {
    "username": "root",
    "password": "password",
    "database": "passport_demo",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "use_env_variable": "JAWSDB_URL",
    "database": "generated database name",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```
<br>

### passport.js
* The passport.js file requires the passport and passport-local dependencies. It contains the code that establishes that we want to login with an email and password. It validates on the sign in page that an account already exists and that the password has been entered correctly. The models folder is imported in order to check inputted emails and passwords against the database and to run sequelize to find them. Passport local sets up the parameters that are being checked. By default LocalStrategy expects to check for username and password, so we make a new LocalStratrgy to check for email instead. The passport.serialize/passport.deserialize at the end of the file create an ongoing session (with the status stored as a cookie) so the user does not have to reauthenticate with each new page loaded. Our new modified passport is then exported.

<br>

### middleware
* Located in the middleware folder is the file "isAuthenticated.js". This file contains the code to authenticate member login status. If req.user is true (aka the user is logged in) then they will have access to page data, otherwise they will be redirected to the login/sign up page. Data on the website is restricted until the user authenticates.

<br>
<br>
<br>
<hr>

## models
<br>

### index.js
* index.js is a boiler plate provided by sequelize to use built in ORMs and handle data. It configures the file system to read through files and read our models and then we assign our db.modelName variables to objects.

<br>

### user.js
* Requires the bcrypt package which encrypts the users password. This is also where create the tables and export them to be used in the rest of the code. We set criteria and validation in our tables here. 

<br>
<br>
<br>
<hr>

## routes
<br>

### api-routes.js
* In the api-routes we require our models to grab table data and require passport to deal with authentication. The api-routes include our post and get methods. We use post methods to grab data and send it to our database and we use get methods to grab database info and provide it for the front end. All of the api routes are exported to server.js.

<br>

### html-routes
* The html-routes page requires path to use relative routes and imports our middleware to check if user is logged in. Here the get methods are created that interact with the HTML the users will see. It handles redirects for non logged in users and sends existing users to the members page.

<br>
<br>
<br>
<hr>

## public
<br>

### js (login,members,signup)
* Interacts with the HTML to grab user created values and feed them to an API for our routes to grab send wherever needed. Validation is done here on user input.

<br>

### html
* The structure of the page the user sees and interacts with. The HTML provides identifiers for buttons and inputs to provide a hook for our front end js files to interact with.

<br>

### stylesheets
* Where all stylings to the html are done.


<br>
<br>
<br>
<hr>


## Deployed Link:
https://eat-da-burger-yum.herokuapp.com/

## Repository Link:
https://github.com/joshglugatch/Eat-Da-Burger


<br>
<br>
<br>


### Author:
Josh Glugatch  

Portfolio link: https://joshglugatch.github.io/josh-glugatch-portfolio/

[![GitHub](https://img.shields.io/badge/github-%23100000.svg?&style=for-the-badge&logo=github&logoColor=white)](https://github.com/joshglugatch)
<br>
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white)](www.linkedin.com/in/joshua-glugatch)



