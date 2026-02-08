# CyrionTrade

A comprehensive cryptocurrency tracking and trading platform built with React and Node.js. CyrionTrade provides real-time cryptocurrency data, portfolio management, and advanced charting capabilities for traders and investors.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Development](#development)
- [Testing](#testing)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Overview

CyrionTrade is a full-stack cryptocurrency platform that enables users to track cryptocurrency prices, manage watchlists, analyze market trends, and access trading signals. The application features a modern, responsive interface with real-time data integration and comprehensive user authentication.

### Key Capabilities

- Real-time cryptocurrency price tracking
- Interactive price charts with historical data
- User authentication and profile management
- Watchlist functionality for favorite cryptocurrencies
- Referral system with bonus rewards
- Marketplace for trading strategies and signals
- Responsive design for desktop and mobile devices

## Features

### Core Features

- **Cryptocurrency Data**
  - Real-time price updates
  - Historical price charts
  - Market cap and volume information
  - Trending coins display
  - Comprehensive coin details

- **User Management**
  - Email and password authentication
  - Wallet connection support
  - User profile management
  - Session management
  - Password reset functionality

- **Portfolio Features**
  - Personal watchlist management
  - Add and remove coins
  - Track favorite cryptocurrencies
  - Portfolio overview

- **Referral System**
  - Unique referral codes
  - Referral tracking
  - Bonus rewards
  - Referral statistics

- **Marketplace**
  - Trading strategies
  - Signal subscriptions
  - Copy trading bots
  - Template marketplace

## Technology Stack

### Frontend

- **Framework:** React 17.0.2
- **UI Library:** Material-UI 4.12.3
- **Routing:** React Router DOM 5.2.0
- **Charts:** Chart.js 3.5.1 with react-chartjs-2
- **HTTP Client:** Axios 0.21.1
- **State Management:** React Context API
- **Build Tool:** React Scripts 5.0.1

### Backend

- **Runtime:** Node.js
- **Framework:** Express 4.18.2
- **Authentication:** Firebase Admin SDK 13.6.0
- **Database:** Firebase Firestore
- **API Integration:** CoinGecko API
- **Security:** Helmet 7.1.0, CORS 2.8.5
- **Validation:** Express Validator 7.0.1
- **Logging:** Morgan 1.10.0

## Prerequisites

Before installing CyrionTrade, ensure you have the following software installed on your system:

- **Node.js:** Version 14.x or higher
- **npm:** Version 6.x or higher (comes with Node.js)
- **Git:** For cloning the repository
- **Firebase Account:** For authentication and database services
- **CoinGecko API Key:** For cryptocurrency data (optional for development)

### System Requirements

- **Operating System:** Windows, macOS, or Linux
- **RAM:** Minimum 4GB recommended
- **Disk Space:** At least 500MB free space

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/cyriontrade.git
cd cyriontrade
```

### 2. Install Server Dependencies

```bash
cd server
npm install
```

### 3. Install Client Dependencies

```bash
cd ../client
npm install
```

## Configuration

### Server Configuration

1. Navigate to the server directory:
```bash
cd server
```

2. Create a `.env` file by copying the example:
```bash
copy .env.example .env
```

3. Configure the following environment variables in `.env`:

```env
# Server Configuration
NODE_ENV=development
PORT=5000

# Firebase Admin SDK
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYour private key here\n-----END PRIVATE KEY-----\n"
FIREBASE_CLIENT_EMAIL=firebase-adminsdk@your-project.iam.gserviceaccount.com

# Firebase Client Config
FIREBASE_API_KEY=your_api_key
FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
FIREBASE_STORAGE_BUCKET=your_project.appspot.com
FIREBASE_MESSAGING_SENDER_ID=your_sender_id
FIREBASE_APP_ID=your_app_id

# CoinGecko API
COINGECKO_API_KEY=your_coingecko_api_key

# CORS Configuration
CORS_ORIGIN=http://localhost:3000
```

### Client Configuration

1. Navigate to the client directory:
```bash
cd ../client
```

2. Create a `.env` file by copying the example:
```bash
copy .env.example .env
```

3. Configure the following environment variables in `.env`:

```env
# API Configuration
REACT_APP_API_URL=http://localhost:5000/api

# Firebase Configuration
REACT_APP_FIREBASE_API_KEY=your_api_key_here
REACT_APP_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
REACT_APP_FIREBASE_PROJECT_ID=your_project_id
REACT_APP_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
REACT_APP_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
REACT_APP_FIREBASE_APP_ID=your_app_id
```

### Firebase Setup

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Authentication with Email/Password provider
3. Create a Firestore database
4. Generate a service account key:
   - Go to Project Settings > Service Accounts
   - Click "Generate New Private Key"
   - Save the JSON file securely
5. Copy the credentials to your `.env` files

### CoinGecko API Setup

1. Sign up for a free account at [CoinGecko](https://www.coingecko.com/en/api)
2. Generate an API key (optional for development)
3. Add the API key to your server `.env` file

## Running the Application

### Development Mode

#### Start the Backend Server

Open a terminal and run:

```bash
cd server
npm run dev
```

The server will start on `http://localhost:5000`

#### Start the Frontend Application

Open a new terminal and run:

```bash
cd client
npm start
```

The application will open automatically in your browser at `http://localhost:3000`

### Production Mode

#### Build the Frontend

```bash
cd client
npm run build
```

#### Start the Production Server

```bash
cd server
npm start
```

## Project Structure

```
cyriontrade/
├── client/                      # Frontend React application
│   ├── public/                  # Static files
│   ├── src/
│   │   ├── components/          # React components
│   │   │   ├── Authentication/  # Auth-related components
│   │   │   ├── Banner/          # Banner components
│   │   │   ├── Bonus/           # Bonus system components
│   │   │   ├── Marketplace/     # Marketplace components
│   │   │   ├── Modals/          # Modal dialogs
│   │   │   ├── Referral/        # Referral system components
│   │   │   ├── CoinInfo.js      # Chart component
│   │   │   ├── CoinsTable.js    # Coin listing table
│   │   │   ├── Header.js        # Navigation header
│   │   │   └── Footer.js        # Footer component
│   │   ├── Pages/               # Page components
│   │   │   ├── HomePage.js      # Landing page
│   │   │   ├── CoinPage.js      # Individual coin details
│   │   │   ├── MarketplacePage.js
│   │   │   └── ...
│   │   ├── config/              # Configuration files
│   │   ├── constants/           # Application constants
│   │   ├── services/            # API service layer
│   │   │   └── api.js           # API client
│   │   ├── utils/               # Utility functions
│   │   ├── App.js               # Main application component
│   │   ├── CryptoContext.js     # Global state context
│   │   └── index.js             # Application entry point
│   ├── .env.example             # Environment variables template
│   └── package.json             # Frontend dependencies
│
├── server/                      # Backend Node.js application
│   ├── routes/                  # API route handlers
│   ├── middleware/              # Express middleware
│   ├── services/                # Business logic services
│   ├── utils/                   # Utility functions
│   ├── server.js                # Server entry point
│   ├── .env.example             # Environment variables template
│   └── package.json             # Backend dependencies
│
├── GUIDE.md                     # Developer test task guide
└── README.md                    # This file
```

## API Documentation

### Base URL

Development: `http://localhost:5000/api`

### Authentication Endpoints

#### POST /api/auth/signup
Create a new user account.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "securepassword",
  "displayName": "John Doe"
}
```

#### POST /api/auth/login
Authenticate a user.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

#### POST /api/auth/logout
Logout the current user.

#### GET /api/auth/verify
Verify authentication token.

### Cryptocurrency Endpoints

#### GET /api/crypto/coins
Get list of cryptocurrencies.

**Query Parameters:**
- `currency` (optional): Currency code (default: USD)

#### GET /api/crypto/coin/:id
Get detailed information for a specific coin.

**Parameters:**
- `id`: Coin identifier (e.g., bitcoin, ethereum)

#### GET /api/crypto/chart/:id
Get historical chart data for a coin.

**Parameters:**
- `id`: Coin identifier

**Query Parameters:**
- `days`: Number of days (1, 30, 90, 365)
- `currency`: Currency code (default: USD)

#### GET /api/crypto/trending
Get trending cryptocurrencies.

**Query Parameters:**
- `currency` (optional): Currency code (default: USD)

### Watchlist Endpoints

#### GET /api/watchlist
Get user's watchlist.

#### POST /api/watchlist
Add a coin to watchlist.

**Request Body:**
```json
{
  "coinId": "bitcoin"
}
```

#### DELETE /api/watchlist/:coinId
Remove a coin from watchlist.

### User Endpoints

#### GET /api/user/profile
Get user profile information.

#### PUT /api/user/profile
Update user profile.

### Referral Endpoints

#### GET /api/referral/code
Get user's referral code.

#### GET /api/referral/stats
Get referral statistics.

#### POST /api/referral/apply
Apply a referral code.

### Bonus Endpoints

#### GET /api/bonus/list
Get available bonuses.

#### GET /api/bonus/active
Get active bonuses for user.

#### POST /api/bonus/claim/:bonusId
Claim a bonus.

## Development

### Code Style

The project follows standard JavaScript/React conventions:

- Use ES6+ syntax
- Functional components with hooks
- Consistent naming conventions
- Proper code comments
- ESLint configuration included

### Development Tools

- **React Developer Tools:** Browser extension for debugging React applications
- **Redux DevTools:** For state management debugging (if applicable)
- **Postman:** For API testing
- **VS Code:** Recommended IDE with ESLint and Prettier extensions

### Hot Reloading

Both client and server support hot reloading during development:

- Frontend: Automatic browser refresh on file changes
- Backend: Nodemon automatically restarts server on file changes

## Testing

### Running Tests

#### Frontend Tests

```bash
cd client
npm test
```

#### Backend Tests

```bash
cd server
npm test
```

### Test Coverage

Generate test coverage report:

```bash
npm test -- --coverage
```

## Deployment

### Frontend Deployment (Vercel)

1. Install Vercel CLI:
```bash
npm install -g vercel
```

2. Deploy from client directory:
```bash
cd client
vercel
```

3. Configure environment variables in Vercel dashboard

### Backend Deployment (Vercel/Heroku)

#### Vercel

1. Deploy from server directory:
```bash
cd server
vercel
```

2. Configure environment variables in Vercel dashboard

#### Heroku

1. Install Heroku CLI
2. Create a new Heroku app:
```bash
heroku create your-app-name
```

3. Set environment variables:
```bash
heroku config:set NODE_ENV=production
heroku config:set PORT=5000
```

4. Deploy:
```bash
git push heroku main
```

### Environment Variables for Production

Ensure all environment variables are properly configured in your deployment platform:

- Set `NODE_ENV=production`
- Configure Firebase credentials
- Set correct CORS origins
- Add CoinGecko API key
- Update API URLs

## Contributing

### Developer Test Task

If you are completing the developer test task, please refer to [GUIDE.md](./GUIDE.md) for detailed requirements and submission guidelines.

### General Contributions

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Submit a pull request

### Contribution Guidelines

- Follow the existing code style
- Write clear commit messages
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Support

For questions, issues, or support:

- Create an issue in the GitHub repository
- Contact the development team
- Check the documentation in [GUIDE.md](./GUIDE.md)

## Acknowledgments

- CoinGecko for cryptocurrency data API
- Firebase for authentication and database services
- Material-UI for React components
- Chart.js for charting capabilities
- The open-source community for various libraries and tools

---

**Version:** 0.2.1  
**Last Updated:** February 2026  
**Maintained by:** CyrionTrade Development Team
