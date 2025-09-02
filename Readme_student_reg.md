1. Student Registration

Endpoint
POST /api/school/students/registration/

Description

Register a new student with name, email, and password. Each email can be registered only once. Passwords are securely hashed before storing in the database.

Request Body
{
  "name": "Akash Sheet",
  "email_id": "akash@gmail.com",
  "password": "mypassword123",
  "confirm_password": "mypassword123"
}

Example Usage
curl -X POST "http://localhost:8000/api/school/students/registration/" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Akash Sheet",
    "email_id": "akash@gmail.com",
    "password": "mypassword123",
    "confirm_password": "mypassword123"
  }'

Sample Success Response
{
  "id": 1,
  "name": "Akash Sheet",
  "email_id": "akash@gmail.com",
  "created_at": "2025-09-02T10:20:30Z",
  "updated_at": "2025-09-02T10:20:30Z"
}

Sample Error Responses

If passwords don’t match:

{
  "confirm_password": "Passwords do not match."
}


If email already exists:

{
  "email_id": "This email is already registered. Please use a different email address."
}
