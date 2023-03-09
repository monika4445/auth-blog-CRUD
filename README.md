# A User-Friendly API for Managing Blog Posts with MongoDB Database and JWT Authentication

## Description

This project is ready for most of the basic back end tasks such as authorization, authentication, email confirmation and CRUD

## Features

* User-friendly user registration and login process
* Secure authentication via JWT
* Email confirmation to ensure account security
* Easy-to-use CRUD operations for managing blog posts
* Robust MongoDB database management
* Seeding to help you get started quickly

### Installing

```
git clone https://github.com/monika4445/auth-blog-CRUD.git
cd auth-blog-CRUD
npm install
```

## Getting Started

To test the application

* Register on https://www.mongodb.com/atlas/database
* Create your free shared database and choose a username and password for it
* Add your username and password to the .env file (you need to create your .env file in the root of the project)
* Example 
MONGO_URI="mongodb+srv://username:password@cluster0.nfa40se.mongodb.net/?retryWrites=true&w=majority"
* Make a temporary gmail account for testing purposes
* Enable 2 factor authentication and click on app passwords (article: https://mailtrap.io/blog/send-emails-with-nodejs/)
* Add your email and password for the app in the .env file
* Example
EMAIL_SENDER='yourchosenemail@gmail.com'
EMAIL_PASSWORD='password'
* Choose a random string as JWT secret or generate it in your terminal
```
node
console.log(crypto.randomBytes(64).toString('hex'));
```
* Copy it and place in in your .env file
* Example
TOKEN_SECRET="yourrandomlygeneratedsecretkey"
* Start the application
```
nodemon server.js
```
* Register via http://localhost:3000/auth/register with username, email, and password in the body as JSON format via Postman or any alternatives
* If successful, you should get a verification email
* Email link should look like this - http://localhost:3000/auth/user/confirm/somerandomlygeneratedjwttoken
* Opening the link will change your username confirmed field to true and show confirmed message in the response
* Login via http://localhost:3000/auth/login with the same email and password
* Your response should have a JSON token
* Place it inside the Authentication tab Bearer Token
* Make a request to http://localhost:3000/posts
* If you get 200 OK and {"posts": []} as a result, everything was successful
* From there you can edit the app based on your needs
* If you want to seed your post database with some random information, run node post_seed.js in the seeds folder, click "y" to delete all previous recrods or anything else to just add data without deleting anything

