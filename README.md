# Daman-Ease API Documentation

Welcome to the **Daman-Ease** API documentation. This README provides a comprehensive overview of the available endpoints, authentication mechanisms, and data structures for the Daman-Ease health-tech platform.

## Table of Contents
- [Overview](#overview)
- [Authentication](#authentication)
- [Base URL](#base-url)
- [API Endpoints](#api-endpoints)
  - [Authentication & Account Management](#authentication--account-management)
  - [Administrative Operations](#administrative-operations)
  - [Consultations](#consultations)
  - [Prescriptions (Ordonnances)](#prescriptions-ordonnances)
  - [User Profile Management](#user-profile-management)
- [Roles](#roles)
- [Contact](#contact)

---

## Overview
**Title:** Daman-Ease API Documentation  
**Version:** 1.0.0  
**Description:** This API powers the Daman-Ease health-tech platform, facilitating communication between patients, doctors, pharmacies, and insurance providers.

---

## Authentication
The API uses **Bearer Authentication (JWT)** for securing its endpoints. 

To access protected routes:
1. Log in or register to receive a JWT token.
2. Include the token in the `Authorization` header of your HTTP requests:
   ```
   Authorization: Bearer <your_jwt_token>
   ```

---

## Base URL
- **Development Server:** `http://localhost:3000/api/v1`

---

## API Endpoints

### Authentication & Account Management
| Method | Endpoint | Summary |
| :--- | :--- | :--- |
| `POST` | `/auth/register` | Register a new user with specific roles. |
| `POST` | `/auth/login` | Log in and receive an authentication token. |
| `GET` | `/auth/me` | Retrieve the authenticated user's profile. |
| `POST` | `/auth/verify-email` | Verify a user's email using a token. |
| `POST` | `/auth/forgot-password` | Request a password reset link. |
| `POST` | `/auth/reset-password` | Set a new password using a reset token. |

### Administrative Operations
*Access restricted to users with the `ADMIN` role.*
| Method | Endpoint | Summary |
| :--- | :--- | :--- |
| `GET` | `/admin/stats` | Retrieve platform-wide statistics. |
| `GET` | `/admin/logs` | View centralized logs (Auth, DB, or API). |

### Consultations
| Method | Endpoint | Summary |
| :--- | :--- | :--- |
| `GET` | `/consultations` | List all consultations (filtered by user role). |
| `POST` | `/consultations` | Create a new medical consultation request. |
| `PATCH` | `/consultations/{id}/status` | Update the status of a consultation (e.g., CONFIRMED, COMPLETED). |

### Prescriptions (Ordonnances)
| Method | Endpoint | Summary |
| :--- | :--- | :--- |
| `GET` | `/ordonnances` | List available prescriptions. |
| `POST` | `/ordonnances` | Create a new prescription (Restricted to **Doctors**). |

### User Profile Management
| Method | Endpoint | Summary |
| :--- | :--- | :--- |
| `GET` | `/users/profile` | Get the current user's profile information. |
| `PATCH` | `/users/profile` | Update profile details (First Name, Last Name). |

---

## Roles
The platform identifies five distinct user roles:
- `PATIENT`
- `DOCTOR`
- `PHARMACY`
- `INSURANCE`
- `ADMIN`

---

## Contact
For any inquiries or support regarding the API, please contact:
- **Name:** API Support
- **Email:** yahyahajji.engineer@gmail.com
