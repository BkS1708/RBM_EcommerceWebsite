# 🛒 RBM Robotics - E-Commerce Website

Welcome to **RBM Robotics’ eCommerce Platform**, a full-stack web application built for selling high-quality robotics components. This project combines a modern frontend with a powerful backend and real-time database integration — all connected seamlessly with email functionality and user authentication.

---

## 🚀 Features

### 🖥️ Frontend (HTML, CSS, Bootstrap, JavaScript)
- **Responsive Design** using **Bootstrap 4** for seamless browsing across devices.
- **Dynamic Product Listings** with "Add to Cart" buttons.
- **Slideshow Section** for most-selling parts.
- **Search Bar with Redirect Logic** — helps users quickly find components based on keywords.
- **"About Us" Team Section** showcasing contributors with LinkedIn profiles.
- **Clipboard Copy Functionality** for quick contact.
- **Feedback Form** for real-time user input.

### 🛍️ Shopping Cart
- Real-time cart system where selected products are listed.
- On clicking **"Proceed"**, an email is sent to the user with:
  - Order Summary
  - Total Price
- Cart data (items + email + total) is saved in MongoDB for recordkeeping.

### 🔐 User Authentication (Node.js + MongoDB)
- **User Registration & Login** functionality.
- Passwords are securely hashed using **bcrypt**.
- Validations for email duplication and missing fields.
  
### 📨 Email Integration
- On order submission, a confirmation **email is sent using Nodemailer**.
- Uses **Gmail SMTP with App Passwords** for authentication.

### 📦 Backend (Node.js + Express + MongoDB)
- Routes for:
  - `/register` – New user registration
  - `/login` – User login
  - `/submit-feedback` – Save feedback
  - `/send-email` – Send order email and save cart details
- MongoDB collections:
  - `users` – Stores login info
  - `feedbacks` – Stores homepage feedback
  - `carts` – Stores order summary (username, email, items, total)
- Backend handles all validation, error management, and data persistence.

### 📊 MongoDB Compass Filtering
To filter for orders containing a specific product name:

```json
{ "items": { "$regex": "Starter Bot FRC", "$options": "i" } }
