# Flask User Authentication with JWT and PostgreSQL

This Flask app implements user authentication and authorization using JWTs, with PostgreSQL as the database backend. It includes user registration, login, and profile retrieval features, along with password hashing using bcrypt. Role-based access control is also supported for protected routes.

## Features
- **User Registration**: Allows new users to register with a username, email, and password.
- **Login**: Users can log in to receive a JWT token for authentication.
- **JWT-based Authentication**: Protected routes require a valid JWT token for access.
- **Role-based Access Control**: Admin or user roles can be assigned to control access to certain routes.
- **Password Hashing**: Passwords are securely hashed using bcrypt.

## Setup

### 1. **Install Dependencies**
Ensure that you have Python 3.x installed. Install the required packages by running:

```bash
pip install -r requirements.txt
```

**`requirements.txt`**:
```
flask
flask-sqlalchemy
flask-jwt-extended
flask-bcrypt
psycopg2-binary
python-dotenv
```

### 2. **Configure PostgreSQL**
Update the `.env` file with your PostgreSQL credentials:

```bash
FLASK_APP=app.py
FLASK_ENV=development
SECRET_KEY=your_secret_key_here
SQLALCHEMY_DATABASE_URI=postgresql://your_user:your_password@localhost:5432/your_db
SQLALCHEMY_TRACK_MODIFICATIONS=False
```

### 3. **Create the Database**
Create a PostgreSQL database by running the following SQL:

```sql
CREATE DATABASE your_db;
```

### 4. **Run the Application**
Start the Flask development server:

```bash
python app.py
```

### 5. **Test Endpoints**
- **Register**: `POST /register`
- **Login**: `POST /login`
- **Profile (Protected)**: `GET /profile` (requires JWT token in the Authorization header)

## Notes
- **Development Mode**: By default, the app runs in development mode (`FLASK_ENV=development`).
- **Security**: Make sure to change `SECRET_KEY` and database credentials for production environments.
