# GolangAuth
This repo shows authentication methods which can be useful for many websites for authenticating users via credentials.

This is a simple authentication service implemented in Go. It uses the Gorilla Mux package to create a RESTful API that handles user registration, login, and logout.


1.Make sure you have Go installed on your machine.
2.Clone this repository.
3.Navigate to the cloned directory in your terminal.
4.build and then run main.go.

The service will start running on localhost:8080.

It contains 3 apis:
1. /register:To register a new user, send a POST request to /register with the following JSON payload:

{
  "username": "abc",
  "email":"abc123@gmail.com",
  "password":"abc@123",
  "first_name": "abc",
  "last_name": "def",
  "date_of_birth": "2000-01-20",
  "bio": "I'm a user."
}

2. \login: The entire procedure is explained below: The client sends login credentials as a POST request to the login API endpoint. The server authenticates the details and, if successful, it generates a JWT. The server returns this to instead of creating a cookie.

{
  "email": "your_email",
  "password": "your_password"
}
 
if Login is sucessful, The respon![signin drawio](https://user-images.githubusercontent.com/76638891/220615185-5bf40187-d296-402c-8ab6-973820aae1f8.svg)
se will also contain an HTTP cookie with the name "session_id". This cookie must be sent with every subsequent request to the service.

3.Logout: To log out, send a GET request to /logout. Here you need to provide a session_id so that it deletes that session_id from mongodb and user gets logout.
![thxgd73x4fv79n9dy6if](https://user-images.githubusercontent.com/76638891/220615245-8b51f641-25ff-4264-b0af-1ca01e5d206b.jpg)
