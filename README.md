# Book-Review

A RESTful API built with **Node.js**, **Express**, and **MongoDB** for managing books and user reviews, complete with user authentication via **JWT**.

---

##  Tech Stack

- Node.js
- Express.js
- MongoDB (with Mongoose)
- JWT for authentication
- bcryptjs for password hashing
- dotenv for environment configuration
- CORS & Morgan for development utilities

---

##  Features

-  User signup and login (JWT-based)
-  Add, list, and view books (with filters and pagination)
-  Submit, update, and delete a review (one review per user per book)
-  Search books by title or author (case-insensitive)
-  Secure API access using auth middleware
-  Pagination on books and reviews
-  Centralized error handling

---

##  Project Setup Instructions

### 1. Clone the Repository


git clone https://github.com/Saif200015/Book-Review.git
cd book-review-api

2. Install Dependencies
npm install

4. Configure Environment Variables
Create a .env file in the root directory:

5. Start the Server
npm run dev
The server should now be running at:http://localhost:5000

 Example API Requests with Postman
 
- Signup
POST /api/signup
{
  "name": "Alice",
  "email": "alice@example.com",
  "password": "password123"
}

POST /api/login

{
  "email": "alice@example.com",
  "password": "password123"
}
Response:
{
  "token": "your-jwt-token"
}
Use this token in authenticated routes:
Authorization: Bearer your-jwt-token

 - Add Book (Authenticated)
POST /api/books
{
  "title": "Atomic Habits",
  "author": "James Clear",
  "genre": "Self-help",
  "description": "Tiny changes, remarkable results."
}

 - Get All Books (With Filters)
GET /api/books?page=1&limit=10&author=James Clear&genre=Self-help

- Get Book Details by ID
GET /api/books/:id
Returns:

Book details

Average rating

Reviews with pagination

- Submit Review (Authenticated)
POST /api/books/:id/reviews
{
  "rating": 5,
  "comment": "Excellent book!"
}

 - Update Your Review
PUT /api/reviews/:id
{
  "rating": 4,
  "comment": "Changed my mind."
}

-  Delete Your Review
DELETE /api/reviews/:id

- Search Books by Title or Author
GET /api/search?query=alchemist

Case-insensitive

Partial matches allowed

Searches both title and author

Example:
http://localhost:5000/api/search?query=habits
