# 📌 User API Documentation

REST API sederhana untuk mengelola data user.

---
Tampilan WEB:
![Preview Index.html](img.png)

## 🔗 Base URL

```
http://localhost:8080/api/users
```

---

# 📦 Endpoints

---

## 1️⃣ Create User

**Endpoint**

```
POST /api/users
```

**Request Body**

```json
{
  "name": "Mufid Ghibran",
  "age": 24
}
```

**Response (201 Created)**

```json
{
  "status": "success",
  "data": {
    "Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
    "age": 24,
    "name": "Mufid Ghibran"
  }
}
```

---

## 2️⃣ Update User

**Endpoint**

```
PUT /api/users/{id}
```

**Path Parameter**

| Parameter | Type | Description |
|-----------|------|------------|
| id | UUID | ID user yang akan diupdate |

**Request Body**

```json
{
  "name": "Mufid Ghibran",
  "age": 20
}
```

**Response (200 OK)**

```json
{
  "status": "success",
  "data": {
    "Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
    "age": 20,
    "name": "Mufid Ghibran"
  }
}
```

---

## 3️⃣ Get All Users

**Endpoint**

```
GET /api/users
```

**Response (200 OK)**

```json
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
```

---

## 4️⃣ Get User By ID

**Endpoint**

```
GET /api/users/{id}
```

**Response (200 OK)**

```json
{
  "status": "success",
  "data": {
    "Id": "9e4f1fe7-41a0-4782-ab71-82fc7b355472",
    "age": 20,
    "name": "Mufid Ghibran"
  }
}
```

---

## 5️⃣ Delete User

**Endpoint**

```
DELETE /api/users/{id}
```

**Response (200 OK)**

```json
{
  "status": "success",
  "message": "Delete user with id 9e4f1fe7-41a0-4782-ab71-82fc7b355472"
}
```

---

# ❗ Standard Error Response

## 400 Bad Request

```json
{
  "status": "error",
  "message": "Invalid request body"
}
```

## 404 Not Found

```json
{
  "status": "error",
  "message": "User not found"
}
```

## 500 Internal Server Error

```json
{
  "status": "error",
  "message": "Internal server error"
}
```

---

# 📘 Data Model

| Field | Type | Description |
|-------|------|------------|
| Id | UUID | Unique identifier |
| name | String | Nama user |
| age | Integer | Umur user |

---

# 🚀 How to Run

1. Clone repository
2. Run the application
3. Server berjalan di port `8080`
4. Test menggunakan Postman atau curl

---

# 🧪 Example curl

## Create User

```bash
curl -X POST http://localhost:8080/api/users \
-H "Content-Type: application/json" \
-d '{"name":"Mufid Ghibran","age":24}'
```

## Get All Users

```bash
curl http://localhost:8080/api/users
```

## Update User

```bash
curl -X PUT http://localhost:8080/api/users/{id} \
-H "Content-Type: application/json" \
-d '{"name":"Mufid Ghibran","age":20}'
```

## Delete User

```bash
curl -X DELETE http://localhost:8080/api/users/{id}
```
