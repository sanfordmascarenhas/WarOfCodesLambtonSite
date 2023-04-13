This instruction manual describes how to create a login application using the Flask web framework and MySQL database. The application allows users to login with a username and password, and it uses session data to track whether a user is logged in.

1. Install Flask and Flask-MySQLdb
Before we start, make sure you have Flask and Flask-MySQLdb installed in your Python environment. You can install them using pip:

pip install Flask Flask-MySQLdb


2. Set up the Database (inital database)
Create a MySQL database called "pythonlogin" and a table called "accounts". The "accounts" table should have three columns: "id", "username", and "password".


![](Screenshots/Initial_db.png)


3. Set up the Flask Application
Create a new Python file and import the necessary modules. Then create a Flask application and set its secret key

In Flask, the secret key is used to secure cookies and the session information. When a user logs in, a session is created on the server-side and a cookie with a session ID is sent to the user's browser. The secret key is used to sign the session cookie to prevent tampering by an attacker.

If an attacker manages to modify the session cookie, they could potentially gain access to the user's session, allowing them to perform actions on behalf of the user. By using a secret key to sign the cookie, Flask ensures that the cookie can't be tampered with, and the user's session remains secure.

Additionally, the secret key is also used for other security-related features in Flask, such as securely storing user passwords or generating random tokens.

![](Screenshots/Session_key.png)

4. Create the Login Route

Define a route for the login page, which will handle both GET and POST requests. In the POST request handler, check if the "username" and "password" fields exist in the submitted form. Then, query the database to check if the user exists and the password is correct. If so, set session data to indicate that the user is logged in and redirect to the home page. If not, display an error message.

![](Screenshots/Login_pg.png)