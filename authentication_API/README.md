# API Documentation

This documentation provides an overview of the API endpoints available in our authentication API. These endpoints allow users to perform various actions such as user registration, authentication, and account management.

## Endpoints

### Register

- URL: `/register/`
- Method: `POST`
- Description: Allows users to register an account.
- Request body:
  - `username`: User's desired username.
  - `email`: User's email address.
  - `password`: User's password.
- Response:
  - Success: HTTP 201 Created
  - Error: HTTP 400 Bad Request

### Login

- URL: `/login/`
- Method: `POST`
- Description: Allows users to log in to their account.
- Request body:
  - `username`: User's username or email.
  - `password`: User's password.
- Response:
  - Success: HTTP 200 OK with authentication token.
  - Error: HTTP 400 Bad Request

### Logout

- URL: `/logout/`
- Method: `POST`
- Description: Allows users to log out of their account.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request

### User Details

- URL: `/user/`
- Method: `GET`
- Description: Retrieves the details of the authenticated user.
- Response:
  - Success: HTTP 200 OK with user details.
  - Error: HTTP 401 Unauthorized

### Verify Email

- URL: `/register/verify-email/`
- Method: `POST`
- Description: Sends a verification email to the user's registered email address for email verification.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request

### Resend Email Verification

- URL: `/register/resend-email/`
- Method: `POST`
- Description: Resends the email verification email to the user's registered email address.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request

### Account Confirm Email

- URL: `/account-confirm-email/<str:key>`
- Method: `GET`
- Description: Redirects the user to the account confirmation page after email verification.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 404 Not Found

### Password Reset

- URL: `/password/reset/`
- Method: `POST`
- Description: Sends a password reset email to the user's registered email address.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request

### Password Reset Confirm

- URL: `/password/reset/confirm/<str:uidb64>/<token>`
- Method: `GET`
- Description: Redirects the user to the password reset confirmation page after clicking the password reset link in the email.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 404 Not Found

### Signup (Social Account)

- URL: `/signup/`
- Method: `GET`
- Description: Allows users to sign up using their social media accounts.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request

### Google Login

- URL: `/google/`
- Method: `GET`
- Description: Initiates the Google login process for authentication.
- Response:
  - Success: HTTP 200 OK
  - Error: HTTP 400 Bad Request
