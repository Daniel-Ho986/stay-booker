# Stay-booker

Stay-booker is a web application that allows users to book, manage, and review hotels. It features full CRUD functionality, user authentication, and authorization, and provides users with a seamless hotel booking experience.

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Routes](#routes)
- [Middleware](#middleware)
- [Demo](#demo)
- [License](#license)

## Features

### Hotels
- **CRUD Operations**: Create, Read, Update, and Delete hotels.
- **Search Functionality**: Users can search for hotels by name or location.
- **Booking Management**: Users can book a hotel and manage their bookings.
- **Hotel Reviews**: Add reviews and ratings for hotels.

### User Management
- **Authentication**: User registration, login, and logout with JWT tokens.
- **Authorization**: Protected routes to ensure only authorized users can perform certain actions.
- **Profile Management**: Users can view and update their profiles and booking history.

### Security
- **Data Validation**: Secure and sanitize user input using `Joi` for validation.
- **Authentication & Authorization**: Secure APIs using JWT tokens and middleware.

### Error Handling
- **404 Error Page**: Provides friendly error messages for non-existent routes.

## Tech Stack

### Backend
- **Node.js**: Runtime environment.
- **Express**: Web framework for Node.js.
- **MongoDB**: NoSQL database.
- **Mongoose**: ODM for MongoDB.
- **JWT**: JSON Web Tokens for authentication.
- **Bcrypt**: Password hashing for security.

### Frontend
- **HTML5/CSS3**: Basic styling and structure for pages.
- **JavaScript**: Adds interactivity and dynamic content to the user interface.

### Middleware & Libraries
- **Joi**: Data validation library.
- **Express-Validator**: Validates incoming request data.
- **JSON Web Token**: Authentication via JWT.
- **bcrypt**: Securely hashes passwords for storage.

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Daniel-Ho986/stay-booker.git
    cd stay-booker
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Environment variables:**
    Create a `.env` file in the root directory and add your configurations:
    ```plaintext
    MONGO_URI=<Your MongoDB URI>
    JWT_SECRET=<Your JWT Secret>
    NODE_ENV=<development | production>
    ```

4. **Run the application:**
    ```bash
    npm run dev
    ```

5. **Access the application:**
    Open your browser and navigate to `http://localhost:3000`.

## Usage

### Routes

- **Authentication**:
  - `POST /auth/register`: Register a new user.
  - `POST /auth/login`: Log in a user.
  - `POST /auth/logout`: Log out the user.

- **Hotels**:
  - `GET /hotels`: List all hotels.
  - `POST /hotels`: Create a new hotel.
  - `GET /hotels/:id`: View a specific hotel.
  - `PUT /hotels/:id`: Update hotel information.
  - `DELETE /hotels/:id`: Delete a hotel.

- **Bookings**:
  - `GET /my-bookings`: List user bookings.
  - `POST /hotels/:id/book`: Book a hotel.
  - `DELETE /my-bookings/:id`: Cancel a booking.

- **Reviews**:
  - `POST /hotels/:id/reviews`: Add a review for a hotel.
  - `DELETE /hotels/:id/reviews/:reviewId`: Delete a review.

## Middleware

- **Authentication & Authorization**:
  - `authMiddleware`: Protect routes, ensuring users are authenticated.
  - `hotelOwnerMiddleware`: Ensure users can only update/delete their own hotels.
  
- **Validation**:
  - `Joi` validation schemas are used to validate input data for hotel creation, bookings, and reviews.

## Demo

#### Hotel List
![Hotel List](public/demo/hotelList.png)

#### Booking Management
![Booking Management](public/demo/booking.png)

#### User Authentication Pages
<div style="display: flex; gap: 10px;">
    <img src="public/demo/login.png" alt="Login Page" height="275" width="40%"/>
    <img src="public/demo/register.png" alt="Registration Page" height="275" width="40%"/>
</div>

## License

This project is licensed under the MIT License.
