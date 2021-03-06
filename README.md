# event-booking-system
An event booking system from an assignment for University.

A demo for this can be found at: [At this Heroku site](https://radiant-mountain-63438.herokuapp.com/)
The link may take some time to load due to Heroku spinning up the site, it's on a free cluster so performance isn't the best.

## Description
This project was an assignment, where we were tasked with creating an event booking system. It was up to us to decide what frameworks and languages we would use. I decided that `Nodejs` would be the most appropriate as the program needed to be fast and with the time frame of the assignment it needed to be easy to setup and create.

The program was created using `NodeJs` with various frameworks. The backend also had an `MySQL server`, mainly because a relational database was more relevant to the specific use case. Otherwise `MongoDB` would have been the better database choice since it is used so frequently with `NodeJs`.

The design was very similar to my personal website (if you couldn’t tell). We wanted something clean and unobtrusive so that it would be easier to mark the assignment.

## Requirements
* `NodeJs`
* `MySQL server`
* `npm`

## Installation
If you would like to install and run this, then the following steps will help.

1. Use the `.env.template` file to create a `.env` file in your root directory with your database details.
  ```
  DB_HOST= # The hostname of your MySQL server. Typically: localhost.
  DB_PORT= # The port of your MySQL server. Typically: 3306,
  DB_USER= # The username of your MySQL server.
  DB_PASS= # The password of your MySQL server.
  DB_NAME= # The database name for your MySQL server. Call it anything you like i.e. event-booking-system
  PORT= # The port of the Node server. Default is 3000 if you don't specify one. Just make sure the port you choose isn't in use by another application.
  SESSION_SECRET= # The secret phrase for sessions used in the app. Can be anything you like make sure it's strong.
  ```

2. Creating the MySQL table will require a MySQL server. Run the `dbcreate.sql` file located in the `sql` folder.

3. In the current directory (where the `app.js` file is located) run the following command: `npm install`
(This will install all of the libraries that the app requires to run.)

4. Once the previous step has been completed you can now run the app: `npm start`
This starts the server and you can find that server on port 3000. 
You can go to your browser at 'localhost:3000' and the server should be working.

## Errors
### MySQL
If you encounter an error such as `Error: ER_NOT_SUPPORTED_AUTH_MODE: Client does not support authentication protocol requested by server; consider upgrading MySQL client`.
You may need to set the following on your MySQL database:
  1. Sign into your MySQL database: `mysql -u root -p`
  2. Use the MySQL databse: `use mysql;`
  3. Run the following command: `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'yourPasswordHere';`

This should solve any further issues related to the auth mode not being supported.
