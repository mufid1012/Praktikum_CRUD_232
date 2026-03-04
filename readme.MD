📌 User API Documentation

REST API sederhana untuk mengelola data user.

🔗 Base URL
http://localhost:8080/api/users
📦 Endpoints
1️⃣ Create User

Endpoint

POST /api/users

Request Body

{
"name": "Mufid Ghibran",
"age": 24
}

Response (Success - 201 Created)

{
"status": "success",
"data": {
"Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
"age": 24,
"name": "Mufid Ghibran"
}
}
2️⃣ Update User

Endpoint

PUT /api/users/{id}

Path Parameter

Parameter	Type	Description
id	UUID	ID user yang akan diupdate

Request Body

{
"name": "Mufid Ghibran",
"age": 20
}

Response (Success - 200 OK)

{
"status": "success",
"data": {
"Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
"age": 20,
"name": "Mufid Ghibran"
}
}
3️⃣ Get All Users

Endpoint

GET /api/users

Response (Success - 200 OK)

{
"status": "success",
"data": [
{
"Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
"age": 20,
"name": "Mufid Ghibran"
}
]
}
4️⃣ Get User By ID

Endpoint

GET /api/users/{id}

Response (Success - 200 OK)

{
"status": "success",
"data": {
"Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
"age": 20,
"name": "Mufid Ghibran"
}
}
5️⃣ Delete User

Endpoint

DELETE /api/users/{id}

Response (Success - 200 OK)

{
"status": "success",
"message": "Delete user with id 9e4f1fe7-41a0-4782-ab71-82fc7b355472"
}
❗ Standard Error Response
400 Bad Request
{
"status": "error",
"message": "Invalid request body"
}
404 Not Found
{
"status": "error",
"message": "User not found"
}
500 Internal Server Error
{
"status": "error",
"message": "Internal server error"
}