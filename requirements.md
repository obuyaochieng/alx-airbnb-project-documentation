

## 📘 **requirements.md**

### **Project:** ALX Airbnb Clone – Backend

### **Repository:** `alx-airbnb-project-documentation`

### **File:** `requirements.md`

---

## 🧩 **1. User Authentication**

### **Functional Requirements**

* Users must be able to **register**, **log in**, and **log out**.
* Passwords must be securely hashed and stored.
* Authentication must use JWT (JSON Web Token) or session-based tokens.
* The system should prevent duplicate email registrations.
* A logged-in user should stay authenticated until the token expires or is revoked.

### **API Endpoints**

| Method | Endpoint                | Description                         |
| ------ | ----------------------- | ----------------------------------- |
| `POST` | `/api/v1/auth/register` | Register a new user                 |
| `POST` | `/api/v1/auth/login`    | Authenticate and return a JWT       |
| `POST` | `/api/v1/auth/logout`   | Revoke the user session/token       |
| `GET`  | `/api/v1/auth/profile`  | Retrieve authenticated user details |

### **Input / Output Specification**

**Register – Input:**

```json
{
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "password": "StrongPass@123"
}
```

**Register – Output:**

```json
{
  "message": "User registered successfully",
  "user_id": "u12345"
}
```

**Login – Input:**

```json
{
  "email": "john@example.com",
  "password": "StrongPass@123"
}
```

**Login – Output:**

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 3600
}
```

### **Validation Rules**

* Email: valid email format and unique.
* Password: minimum 8 characters, must include letters, numbers, and a symbol.
* Names: only alphabetic characters allowed.

### **Performance Criteria**

* Response time < 300ms under normal load.
* Token validation must be completed within 100ms.
* Should handle at least 1000 concurrent authentication requests.

---

## 🏠 **2. Property Management**

### **Functional Requirements**

* Registered hosts can **add, edit, and delete** properties.
* Each property includes title, description, location, price, images, and availability.
* Non-owners cannot modify or delete other users’ listings.
* Public users can **view** available properties with filters.

### **API Endpoints**

| Method   | Endpoint                 | Description                       |
| -------- | ------------------------ | --------------------------------- |
| `POST`   | `/api/v1/properties`     | Create a new property (host only) |
| `GET`    | `/api/v1/properties`     | Retrieve list of all properties   |
| `GET`    | `/api/v1/properties/:id` | Retrieve a single property        |
| `PUT`    | `/api/v1/properties/:id` | Update property details           |
| `DELETE` | `/api/v1/properties/:id` | Delete property (owner only)      |

### **Input / Output Specification**

**Create Property – Input:**

```json
{
  "title": "Modern Apartment in Nairobi",
  "description": "A fully furnished apartment with WiFi.",
  "location": "Nairobi, Kenya",
  "price_per_night": 80,
  "images": ["img1.jpg", "img2.jpg"],
  "availability": true
}
```

**Create Property – Output:**

```json
{
  "message": "Property created successfully",
  "property_id": "p6789"
}
```

### **Validation Rules**

* Title: 5–100 characters.
* Price: numeric, must be > 0.
* Location: required.
* Only authenticated users (role = host) can create or modify properties.

### **Performance Criteria**

* Support pagination for large datasets.
* Fetch all properties within 500ms under normal load.
* Image uploads must be handled asynchronously (e.g., via background workers).

---

## 📅 **3. Booking System**

### **Functional Requirements**

* Authenticated users can **book** available properties.
* The system must prevent **double-booking** for the same dates.
* Hosts can view and manage all bookings for their properties.
* Users can cancel bookings within policy constraints.

### **API Endpoints**

| Method   | Endpoint               | Description                 |
| -------- | ---------------------- | --------------------------- |
| `POST`   | `/api/v1/bookings`     | Create a new booking        |
| `GET`    | `/api/v1/bookings`     | Get all bookings for a user |
| `GET`    | `/api/v1/bookings/:id` | View a specific booking     |
| `DELETE` | `/api/v1/bookings/:id` | Cancel a booking            |

### **Input / Output Specification**

**Create Booking – Input:**

```json
{
  "property_id": "p6789",
  "check_in": "2025-11-10",
  "check_out": "2025-11-15",
  "guests": 2
}
```

**Create Booking – Output:**

```json
{
  "message": "Booking confirmed",
  "booking_id": "b1234",
  "total_price": 400
}
```

### **Validation Rules**

* `check_in` must be before `check_out`.
* Property must exist and be available.
* Guests: minimum 1, maximum 10.
* User must be authenticated.

### **Performance Criteria**

* Booking confirmation within 400ms.
* Concurrent booking conflict detection ≤ 100ms.
* System should handle 500 concurrent booking requests.

---

## ⚙️ **General System Requirements**

* **Language:** Python (Flask/Django/FastAPI) or Node.js (Express)
* **Database:** PostgreSQL / MySQL
* **Authentication:** JWT or OAuth2
* **Error Handling:** Consistent JSON-based responses
* **Security:** Input sanitization, HTTPS, password hashing (bcrypt/argon2)

---

### ✅ **Deliverable Checklist**

* [x] File name: `requirements.md`
* [x] Location: Root of `alx-airbnb-project-documentation` repo
* [x] Commit message:

  ```
 

---


