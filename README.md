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
* The server.js file is where we grab our required packages and set up our server. We create our "db" variable requiring our models to setup how our database will handle info. The express, express-session, and passport variables are established to be use for server functionality. We establish which port should be used. We also configure Express to parse data, use the static folder, create express sessions per user login, and sync our database. 

<br>
<br>
<br>


## config

### middleware



<br>
<br>
<br>

### models
 
<br>

<br>
<br>
<br>

### routes

<br>

<br>
<br>
<br>

### public
 
<br>

<br>




<br>
<br>
<br>


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



