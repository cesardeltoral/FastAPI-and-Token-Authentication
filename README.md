FastAPI JWT Authentication Example
This project demonstrates how to implement JWT-based authentication using FastAPI. It includes user management, secure password handling, and token-based authentication for protecting API endpoints.

Features
User Authentication: Validate user credentials and generate access tokens.
JWT Tokens: Stateless authentication with token expiration.
Password Hashing: Securely store user passwords using bcrypt.
Protected Endpoints: Restrict access to authorized users.
Requirements
Python 3.8+
FastAPI
Passlib
PyJWT (JOSE library)
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/your-repo/fastapi-jwt-auth
cd fastapi-jwt-auth
Create and activate a virtual environment:

bash
Copy code
python -m venv venv
source venv/bin/activate # On Windows: venv\Scripts\activate
Install the dependencies:

bash
Copy code
pip install fastapi uvicorn python-jose passlib[bcrypt]
Usage
Run the application:

bash
Copy code
uvicorn main:app --reload
Access the interactive API docs at:

http://127.0.0.1:8000/docs
Use the /token endpoint to obtain a JWT token by providing valid credentials (username and password).

Access protected endpoints by including the token in the Authorization header:

plaintext
Copy code
Authorization: Bearer <your_access_token>
Endpoints
POST /token: Authenticate and generate an access token.
GET /users/me/: Retrieve the current user's details.
GET /users/me/items: Retrieve items owned by the authenticated user.
Example User
The app uses an in-memory database (db) with a sample user:

Username: cesar
Password: password123 (hashed using bcrypt)
Security Notes
Replace SECRET_KEY with a secure random string for production.
Consider using a database for user storage instead of the in-memory dictionary.
