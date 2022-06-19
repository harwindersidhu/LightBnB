# LightBnB
It's all about that database. We build the back-end queries that allow users to search for accommodations in an online travel app. We will connect to a `PostgreSQL` database using `Node's postgres library` and write the queries that deliver the right data to the front end.

## Project Structure

```
├── 1_queries
├── LightBnB_WebApp 
│    ├── public
│    │   ├── index.html
│    │   ├── javascript
│    │   │   ├── components 
│    │   │   │   ├── header.js
│    │   │   │   ├── login_form.js
│    │   │   │   ├── new_property_form.js
│    │   │   │   ├── property_listing.js
│    │   │   │   ├── property_listings.js
│    │   │   │   ├── search_form.js
│    │   │   │   └── signup_form.js
│    │   │   ├── index.js
│    │   │   ├── libraries
│    │   │   ├── network.js
│    │   │   └── views_manager.js
│    │   └── styles
│    ├── sass
│    └── server
│      ├── apiRoutes.js
│      ├── database.js
│      ├── json
│      ├── server.js
│      └── userRoutes.js
├── migrations
└── seeds

```
* `1_queries` contains some SELECT queries on lightbnb database tables.
* `LightBnB_WebApp` is an app which was not working with original database. We connected it with database and made it work with original database.
  * `public` contains all of the HTML, CSS, and client side JavaScript. 
    * `index.html` is the entry point to the application. It's the only html page because this is a single page application.
    * `javascript` contains all of the client side javascript files.
      * `index.js` starts up the application by rendering the listings.
      * `network.js` manages all ajax requests to the server.
      * `views_manager.js` manages which components appear on screen.
      * `components` contains all of the individual html components. They are all created using jQuery.
  * `sass` contains all of the sass files. 
  * `server` contains all of the server side and database code.
    * `server.js` is the entry point to the application. This connects the routes to the database.
    * `apiRoutes.js` and `userRoutes.js` are responsible for any HTTP requests to `/users/something` or `/api/something`. 
    * `json` is a directory that contains a bunch of dummy data in `.json` files.
    * `database.js` is responsible for all queries to the database. It was not connected to any database, all it does was return data from `.json` files. Now it is working with database.
* `migrations` contains queries to create the required tables in database.
* `seeds` contains queries to insert data into the tables.

## Getting Started

1. Install dependencies using the `npm install` command.
2. Initiate `psql` session in your project directory, create database `lightbnb` and then run `migrations` and `seeds` files.
3. cd into the LightBnB_WebApp directory. Run the app using the `npm run local` command. 
4. Go to <http://localhost:3000/> in your browser.

## Dependencies

- Express
- Node 5.10.x or above
- body-parser
- bcrypt
- cookie-session
- nodemon
- pg
