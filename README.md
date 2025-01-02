# User Authentication with Express

This is a simple user authentication system built with Express, PostgreSQL, and Passport. The application allows users to register, log in, and authenticate using Google. It also includes session management and password hashing.

## Features

- **User Registration**:
  - Users can register with an email and password.
  - Passwords are securely hashed using **bcrypt** before storing in the database.
  
- **User Login**:
  - Users can log in using their registered credentials.
  - Authentication is handled using **Passport.js** with a **Local Strategy**.

- **Google Authentication**:
  - Users can log in using their Google account via **Passport's Google OAuth 2.0 strategy**.

- **Session Management**:
  - Users remain logged in between requests using **express-session**.

- **Secrets Page**:
  - Once authenticated, users are redirected to a "secrets" page where they can access private content.

## Technologies Used

This application uses the following technologies:

- **Express**: A minimal and flexible Node.js web application framework.
- **Passport**: An authentication middleware for Node.js that supports various strategies, including local login and Google OAuth.
- **bcrypt**: A library used to hash passwords securely before storing them in the database.
- **PostgreSQL**: A powerful, open-source relational database used for storing user credentials.
- **Google OAuth2**: An authentication strategy for logging in using Google accounts via Passport.js.
- **express-session**: A session middleware that manages user sessions to keep users logged in.
- **dotenv**: A module used to load environment variables from a `.env` file for better security and configuration management.

## Routes

### `GET /`

- Renders the **home** page.

### `GET /login`

- Renders the **login** page.

### `GET /register`

- Renders the **registration** page.

### `GET /logout`

- Logs the user out and redirects to the home page.

### `GET /secrets`

- If the user is authenticated, renders the **secrets** page with private content.
- If the user is not authenticated, redirects to the **login** page.

### `GET /auth/google`

- Redirects the user to Google's OAuth 2.0 authentication page.

### `GET /auth/google/secrets`

- Handles the callback from Google after authentication.
- Redirects to the **secrets** page if successful, or the **login** page if failed.

### `POST /login`

- Authenticates the user using their email and password.
- Redirects to the **secrets** page on success or the **login** page on failure.

### `POST /register`

- Registers a new user with email and password.
- If the user already exists, redirects to the **login** page.
- Hashes the password using **bcrypt** before storing it in the database.

## License

This project is licensed under the **MIT License**.


