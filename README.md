# UserManagementAPI

## 📌 Overview

UserManagementAPI is an ASP.NET Core Web API project that demonstrates basic user registration functionality with secure password hashing using Microsoft Identity’s `PasswordHasher`. It utilizes Entity Framework Core with a Code First approach to store user data.

---

## ⚙️ Features

- ✅ Register users with email and password
- ✅ Hash passwords before saving
- ✅ Retrieve individual or all users
- ✅ Model validation using `[Required]` and `[EmailAddress]`
- ✅ Entity Framework Core Code First
- ✅ Organized folder structure

---

## 📂 Folder Structure

```
UserManagementAPI/
│
├── Controllers/
│   └── UsersController.cs
│
├── Models/
│   └── User.cs
│
├── DTOs/
│   ├── RegisterUserRequest.cs
│   └── UserResponse.cs
│
├── Helpers/
│   └── PasswordHasherHelper.cs
│
├── Data/
│   └── ApplicationDbContext.cs
│
├── Program.cs
└── appsettings.json
```

---

## 🔐 Technologies Used

- ASP.NET Core 8.0
- Entity Framework Core (In-Memory DB or SQL Server)
- Microsoft Identity PasswordHasher
- RESTful API Structure
- Swagger for testing

---

## 🔄 API Endpoints

### 👤 Register User
**POST** `/api/users/register`  
**Body:**
```json
{
  "email": "user@example.com",
  "password": "MySecurePassword123"
}
```

---

### 👀 Get All Users
**GET** `/api/users`  
Returns a list of all registered users (only Id and Email).

---

### 🔍 Get User by ID
**GET** `/api/users/{id}`  
Returns a single user (only Id and Email).

---

## 🧠 How Passwords Are Protected

Passwords are never stored as plain text. Instead, the project uses:

```csharp
Microsoft.AspNetCore.Identity.PasswordHasher<string>
```

This hashes and salts the password with a secure algorithm before saving it to the database.

---

## ▶️ Getting Started

### 1. Clone the Project

```bash
git clone https://github.com/your-username/UserManagementAPI.git
cd UserManagementAPI
```

### 2. Run with Visual Studio

- Open `UserManagementAPI.sln`
- Press **F5** to run
- Swagger UI will open automatically at `https://localhost:xxxx/swagger`

---

## 📌 Notes

- Default setup uses **InMemoryDatabase**, change to SQL Server in `Program.cs` for production.
- This project is for educational/demo purposes.

---

## 📬 Contact

For suggestions or feedback, please reach out via [GitHub Issues](https://github.com/your-username/UserManagementAPI/issues)

---
