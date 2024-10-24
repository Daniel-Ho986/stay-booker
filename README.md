# Stay-booker

[Stay Booker](https://stay-booker.onrender.com/) is a hotel booking application that allows users to search for hotels, manage bookings, and add their own hotels. The project includes a robust authentication system, hotel search functionality, and integration with payment gateways for hotel bookings.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
  - [Running the Project](#running-the-project)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Features

- **User Authentication**: Register, sign in, sign out, and validate sessions.
- **Hotel Search**: Users can search for hotels based on destination, date, price, and other filters.
- **Hotel Management**: Registered users can add, edit, and manage their own hotels.
- **Room Booking**: Users can book rooms and pay through integrated payment systems.
- **Booking Management**: View and manage your bookings.
- **Responsive Design**: Optimized for mobile and desktop devices.

## Tech Stack

- **Frontend**: React, TypeScript, React Query, React Router
- **Backend**: Node.js, Express, TypeScript
- **Database**: MongoDB (or any other database, depending on your setup)
- **Authentication**: JSON Web Tokens (JWT) with session management
- **Testing**: Playwright for end-to-end testing

## Getting Started

### Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Daniel-Ho986/stay-booker.git
   cd stay-booker

2. **Backend Setup**:

   ```bash
   cd backend
   npm install

3. **Frontend Setup**:

   ```bash
   cd frontend
   npm install

4. **E2E Tests Setup**:

   ```bash
   cd e2e-tests
   npm install

### Environment Variables

Create `.env` files in both `backend/` and `frontend/` directories with the following variables:

1. **Backend** (`backend/.env`)

    ```bash
    VITE_API_BASE_URL=http://localhost:5000
    DATABASE_URL=mongodb://localhost:27017/stay-booker
    JWT_SECRET=your_jwt_secret

2. **Frontend** (`frontend/.env`)

    ```bash
    VITE_API_BASE_URL=http://localhost:5000

### Running the Project

1. **Run the Backend**:
    Navigate to the `backend` directory and start the server:

    ```bash
    npm run dev

    The backend will be running on `http://localhost:5000`.

2. **Run the Frontend**:
     Navigate to the `frontend` directory and start the frontend:

    ```bash
    npm run dev

    The frontend will be running on `http://localhost:3000`.

3. **Run End-to-End Tests**:
     Navigate to the `e2e-tests` directory and run the tests:

    ```bash
    npx playwright test

## API Endpoints

### User Authentication

- `POST /api/users/register`: Register a new user.
- `POST /api/auth/login`: Log in as an existing user.
- `POST /api/auth/logout`: Log out the current user.
- `GET /api/users/me`: Fetch the current user's profile.
- `GET /api/auth/validate-token`: Validate the user's session token.

### Hotel Management

- `POST /api/my-hotels`: Add a new hotel.
- `GET /api/my-hotels`: Fetch the user's hotels.
- `GET /api/my-hotels/:hotelId`: Fetch a specific hotel by ID.
- `PUT /api/my-hotels/:hotelId`: Update an existing hotel.

### Hotel Search and Booking

- `GET /api/hotels`: Fetch all available hotels.
- `GET /api/hotels/search`: Search for hotels based on filters.
- `GET /api/hotels/:hotelId`: Fetch a specific hotel by ID.
- `POST /api/hotels/:hotelId/bookings`: Book a room at a specific hotel.
- `POST /api/hotels/:hotelId/bookings/payment-intent`: Create a payment intent for booking.

## License

This project is licensed under the MIT License.