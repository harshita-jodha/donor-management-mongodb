# Commons — Charity Donation Platform

A full-stack charity donation platform built with **React, Node.js, Express, and MongoDB**. Commons transforms a static charity website into a dynamic web application with user authentication, charity causes, donation tracking, volunteer applications, and contact management.

## Features

- **User Authentication:** Registration and login using JWT authentication and bcrypt password hashing.
- **Cause Management:** Browse charity causes and manage them through admin endpoints.
- **Donation Management:** Submit donations and track donation history.
- **Volunteer Applications:** Submit and manage volunteer applications.
- **Contact Management:** Submit contact messages and manage them through admin endpoints.
- **Admin Access:** Protected endpoints for managing causes, donations, volunteers, and contact messages.
- **MongoDB Integration:** Persist application data using MongoDB and Mongoose.
- **Responsive Frontend:** React application built with Vite.

## Tech Stack

**Frontend**
- React
- Vite
- JavaScript
- HTML and CSS

**Backend**
- Node.js
- Express.js
- Mongoose
- MongoDB
- JSON Web Tokens (JWT)
- bcrypt

## Project Structure
```text
donor-management-mongodb/
├── .vscode/    # Editor configuration
├── backend/    # Node.js, Express API and MongoDB integration
├── frontend/   # React frontend application
└── README.md   # Project documentation
```

## Prerequisites

- Node.js 18 or later
- npm
- MongoDB local installation or a MongoDB Atlas cluster

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/harshita-jodha/donor-management-mongodb.git
cd commons-charity-app
```


### 2. Configure the Backend

```bash
cd backend
npm install
```

Copy `.env.example` to `.env` and configure your environment variables:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_long_random_secret
JWT_EXPIRES_IN=7d
CLIENT_ORIGIN=http://localhost:5173
```

Use your own MongoDB connection string and a strong, unique JWT secret.

### 3. Seed Sample Data

If your project includes the seed script, run:

```bash
npm run seed
```

This inserts the sample causes and the demo admin account configured by the project.

### 4. Start the Backend

```bash
npm run dev
```

The API runs at `http://localhost:5000`.

### 5. Configure and Start the Frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

Keep both the backend and frontend running during development.

## API Overview

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/auth/register` | Register a user |
| POST | `/api/auth/login` | Log in |
| GET | `/api/auth/me` | Get the current user's profile |
| GET | `/api/causes` | List active causes |
| GET | `/api/causes/:idOrSlug` | Get a cause |
| POST | `/api/causes` | Create a cause (admin) |
| PUT | `/api/causes/:id` | Update a cause (admin) |
| DELETE | `/api/causes/:id` | Deactivate a cause (admin) |
| POST | `/api/donations` | Submit a donation |
| GET | `/api/donations/mine` | View personal donation history |
| GET | `/api/donations` | View all donations (admin) |
| POST | `/api/volunteers` | Submit a volunteer application |
| GET | `/api/volunteers` | View applications (admin) |
| POST | `/api/contact` | Submit a contact message |
| GET | `/api/contact` | View messages (admin) |

Private and admin endpoints require a JWT access token in the `Authorization: Bearer <token>` header.

## Important Note About Payments

The current donation flow records donation information but does not process real payments through a payment gateway. A payment provider such as Razorpay or Stripe must be integrated before accepting real online payments.

## Security Notes

- Keep `.env` files and database credentials out of version control.
- Use strong secrets and secure admin credentials.
- Change or remove default demo admin credentials before deployment.
- Never treat a donation as paid until the payment provider confirms it.

## Future Improvements

- Integrate a secure online payment gateway.
- Add donation receipts and reporting.
- Improve search and filtering for charity causes.
- Deploy the frontend and backend.

## Author

Harshita Rathore

## License

Add a license if you intend to distribute this project under an open-source license.
