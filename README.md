# Tour Booking Application API

A RESTful API for a tour booking application built with Node.js, Express, and MongoDB. This API provides endpoints for managing tours, users, reviews, and bookings.

## Features

- 🔐 JWT Authentication & Authorization
- 📍 Geospatial Queries
- 📧 Email Integration
- 💳 Stripe Payment Integration
- 📊 Advanced Filtering, Sorting, and Pagination
- 🛡️ Security Features (Rate Limiting, XSS Protection, etc.)
- 📝 Comprehensive Error Handling
- 📱 Responsive Design

## Tech Stack

- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for Authentication
- Pug for Server-Side Rendering
- Stripe for Payment Processing
- Nodemailer for Email Services

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- npm or yarn

## Installation

1. Clone the repository:
```bash
git clone https://github.com/ZoubairAntifi/tour-booking-app.git
cd tour-booking-app
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory and add the following variables:
```env
NODE_ENV=development
PORT=3000
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=90d
STRIPE_SECRET_KEY=your_stripe_secret_key
EMAIL_FROM=your_email
EMAIL_USERNAME=your_email_username
EMAIL_PASSWORD=your_email_password
EMAIL_HOST=your_email_host
EMAIL_PORT=your_email_port
```

4. Start the development server:
```bash
npm run dev
```

## API Documentation

### Authentication Endpoints

- `POST /api/v1/users/signup` - Register a new user
- `POST /api/v1/users/login` - Login user
- `GET /api/v1/users/logout` - Logout user
- `POST /api/v1/users/forgotPassword` - Request password reset
- `PATCH /api/v1/users/resetPassword/:token` - Reset password

### Tour Endpoints

- `GET /api/v1/tours` - Get all tours
- `GET /api/v1/tours/:id` - Get a specific tour
- `POST /api/v1/tours` - Create a new tour (Admin only)
- `PATCH /api/v1/tours/:id` - Update a tour (Admin only)
- `DELETE /api/v1/tours/:id` - Delete a tour (Admin only)
- `GET /api/v1/tours/tour-stats` - Get tour statistics (Admin only)
- `GET /api/v1/tours/monthly-plan/:year` - Get monthly plan (Admin only)

### Review Endpoints

- `GET /api/v1/reviews` - Get all reviews
- `POST /api/v1/reviews` - Create a new review
- `GET /api/v1/reviews/:id` - Get a specific review
- `PATCH /api/v1/reviews/:id` - Update a review
- `DELETE /api/v1/reviews/:id` - Delete a review

### Booking Endpoints

- `GET /api/v1/bookings` - Get all bookings
- `POST /api/v1/bookings/checkout-session/:tourId` - Create checkout session
- `GET /api/v1/bookings/checkout-session/:sessionId` - Get checkout session

## Query Parameters

### Tours

- `page`: Page number for pagination
- `limit`: Number of items per page
- `sort`: Sort field (price, ratingsAverage, etc.)
- `fields`: Fields to return
- `duration[gte]`: Filter tours with duration greater than or equal to
- `duration[lte]`: Filter tours with duration less than or equal to
- `price[gte]`: Filter tours with price greater than or equal to
- `price[lte]`: Filter tours with price less than or equal to
- `difficulty`: Filter by difficulty level
- `ratingsAverage[gte]`: Filter by minimum rating

## Error Handling

The API uses a global error handling middleware that provides consistent error responses across all endpoints. Errors are categorized into:

- Operational Errors (400, 401, 403, 404, etc.)
- Programming Errors (500)

## Security Features

- Data Sanitization against XSS
- Data Sanitization against NoSQL query injection
- Parameter Pollution protection
- Security HTTP headers
- Rate limiting
- Password hashing
- JWT authentication
- Secure cookie handling


## Acknowledgments

- Jonas Schmedtmann for the original course and inspiration
