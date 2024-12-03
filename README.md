**ZWEB**

This project is a comprehensive User Management API built with Node.js, Express.js, and MongoDB. It offers a wide array of features for user registration, authentication, profile management, and administrative functions.

### Features

**General User Features**
- **User Registration:** Securely register new users.
- **Email Verification:** Verify user email addresses using tokens.
- **Login:** Authenticate users and provide access tokens.
- **Profile Update:** Update user profiles, including usernames and avatars.
- **Password Management:** Update passwords or reset forgotten ones.
- **Logout:** Securely log users out of the system.
- **Avatar Upload:** Upload and manage profile pictures.
- **Token Management:** Refresh expired tokens without requiring re-authentication.

**Admin Features**
- **User Management:** Create, block, unblock, and delete users.
- **Alert System:** Send notifications or alerts to users.
- **Page Management:** Manage user-associated pages, including deletion.

### Validation and Error Handling
- **Input Validation:** Implement strong validation for user inputs using Joi.
- **Error Responses:** Provide detailed and user-friendly error responses.

### Security
- Passwords are hashed using bcrypt.
- Tokens are securely generated and validated using JWT.
- Avatar uploads are validated for file type and size.

### Endpoints

**General User Endpoints**
| Method | Endpoint                     | Description                             | Authentication |
|--------|------------------------------|-----------------------------------------|-----------------|
| POST   | /                            | Register a new user                    | No              |
| GET    | /verify/:token               | Verify email                            | No              |
| POST   | /login                       | Log in a user                          | No              |
| PUT    | /update-username             | Update username                        | Yes             |
| DELETE | /delete                      | Delete user                            | Yes             |
| GET    | /refresh-token               | Refresh access token                   | Yes             |
| POST   | /upload                      | Upload user avatar                     | Yes             |
| GET    | /avatar                      | Get user avatar                        | Yes             |
| GET    | /me                          | Get user details                       | Yes             |
| GET    | /logout-user                 | Log out user                           | Yes             |
| POST   | /update-password             | Update user password                   | Yes             |
| POST   | /resend-email                | Resend verification email               | No              |
| POST   | /forget-password             | Send password reset email              | No              |
| POST   | /reset-password/:token       | Reset password                         | No              |

**Admin Endpoints**
| Method | Endpoint                     | Description                             | Authentication  |
|--------|------------------------------|-----------------------------------------|------------------|
| POST   | /admin-create-user           | Create a new user as admin             | Yes (Admin)      |
| POST   | /admin-block-user            | Block a user                           | Yes (Admin)      |
| POST   | /admin-unblock-user          | Unblock a user                         | Yes (Admin)      |
| GET    | /admin-get-users             | Get all users                          | Yes (Admin)      |
| DELETE | /admin-delete-user           | Delete a user                          | Yes (Admin)      |

### Technologies Used
- **Node.js:** Backend runtime environment.
- **Express.js:** Web framework.
- **MongoDB:** Database for storing user data.
- **Multer:** Handling file uploads.
- **Joi:** For input validation.
- **JWT:** For authentication tokens.
- **Sharp:** Image processing for avatars.
- **Bcrypt:** For password hashing.
