# Basic-api

Movie API with FastAPI
Overview
This is a simple FastAPI application that provides CRUD operations for managing movies. It includes endpoints for listing movies, retrieving a specific movie by ID, creating a new movie, updating an existing movie, and deleting a movie. Additionally, there's an authentication mechanism using JWT to secure certain endpoints.

Endpoints
1. Home
URL: /
Method: GET
Description: Returns a simple HTML response with the message "Hello world."
2. Login
URL: /login
Method: POST
Description: Authenticates a user and generates a JWT token.
Request Body:
json
Copy code
{
  "email": "admin@gmail.com",
  "password": "admin"
}
Response:
Successful login:
json
Copy code
{
  "token": "<JWT_TOKEN>"
}
Unsuccessful login:
json
Copy code
{
  "detail": "Credenciales invalidas"
}
3. Get Movies
URL: /movies
Method: GET
Description: Retrieves a list of movies.
Authentication: Requires a valid JWT token for access.
4. Get Movie by ID
URL: /movies/{id}
Method: GET
Description: Retrieves details of a specific movie by ID.
Path Parameter:
id: ID of the movie (integer).
5. Get Movies by Category
URL: /movies/
Method: GET
Description: Retrieves a list of movies filtered by category.
Query Parameter:
category: Movie category (string).
6. Create Movie
URL: /movies
Method: POST
Description: Adds a new movie to the list.
Request Body:
json
Copy code
{
  "title": "Movie Title",
  "overview": "Movie Overview",
  "year": 2022,
  "rating": 9.5,
  "category": "Action"
}
7. Update Movie
URL: /movies/{id}
Method: PUT
Description: Updates details of a specific movie by ID.
Path Parameter:
id: ID of the movie (integer).
Request Body:
json
Copy code
{
  "title": "Updated Movie Title",
  "overview": "Updated Movie Overview",
  "year": 2023,
  "rating": 8.0,
  "category": "Adventure"
}
8. Delete Movie
URL: /movies/{id}
Method: DELETE
Description: Deletes a specific movie by ID.
Path Parameter:
id: ID of the movie (integer).
Authentication
JWT (JSON Web Token) is used for authentication. To access certain endpoints, include the JWT token in the Authorization header.
