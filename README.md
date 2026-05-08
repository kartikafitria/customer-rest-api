# Customer REST API

REST API sederhana untuk manajemen data customer menggunakan Laravel 10 dan MySQL.  
Project ini dibuat sebagai studi kasus CRUD Backend API dengan fitur validation, pagination, dan custom JSON response.

---

## Features

- Create customer
- Get all customers
- Get customer detail
- Update customer
- Delete customer
- Pagination
- Input validation
- Custom JSON response format

---

## Tech Stack

- PHP 8.1
- Laravel 10
- MySQL

---

## Customer Data Structure

| Field | Type |
|---|---|
| id | Integer |
| name | String |
| email | String |
| phone_number | String |
| address | Text |
| created_at | Timestamp |
| updated_at | Timestamp |

---

## Installation

```bash
git clone https://github.com/kartikafitria/customer-rest-api.git

cd customer-rest-api

composer install

cp .env.example .env

php artisan key:generate

php artisan migrate

php artisan serve
```

---

## API Documentation

## Base URL

```bash
http://127.0.0.1:8000/api
```

---

## 1. Get All Customers

### Endpoint

```http
GET /customers
```

### Response

```json
{
  "status": true,
  "message": "Customer list retrieved successfully",
  "data": {
    "current_page": 1,
    "data": []
  }
}
```

---

## 2. Get Customer Detail

### Endpoint

```http
GET /customers/{id}
```

### Response

```json
{
  "status": true,
  "message": "Customer detail retrieved",
  "data": {
    "id": 1,
    "name": "Kartika",
    "email": "kartika@gmail.com",
    "phone_number": "08123456789",
    "address": "Yogyakarta"
  }
}
```

---

## 3. Create Customer

### Endpoint

```http
POST /customers
```

### Request Body

```json
{
  "name": "Kartika",
  "email": "kartika@gmail.com",
  "phone_number": "08123456789",
  "address": "Yogyakarta"
}
```

### Response

```json
{
  "status": true,
  "message": "Customer created successfully",
  "data": {
    "id": 1,
    "name": "Kartika",
    "email": "kartika@gmail.com",
    "phone_number": "08123456789",
    "address": "Yogyakarta"
  }
}
```

---

## 4. Update Customer

### Endpoint

```http
PUT /customers/{id}
```

### Request Body

```json
{
  "name": "Kartika Fitria",
  "email": "kartikafitria@gmail.com",
  "phone_number": "08123456789",
  "address": "Klaten"
}
```

### Response

```json
{
  "status": true,
  "message": "Customer updated successfully",
  "data": {
    "id": 1,
    "name": "Kartika Fitria",
    "email": "kartikafitria@gmail.com",
    "phone_number": "08123456789",
    "address": "Klaten"
  }
}
```

---

## 5. Delete Customer

### Endpoint

```http
DELETE /customers/{id}
```

### Response

```json
{
  "status": true,
  "message": "Customer deleted successfully",
  "data": null
}
```

---

# Validation Rules

| Field | Rules |
|---|---|
| name | required |
| email | required, email, unique |
| phone_number | required |
| address | required |

---

# Example Success Response Format

```json
{
  "status": true,
  "message": "Success message",
  "data": {}
}
```
