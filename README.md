# Banking API with JWT Authentication

A minimal Node.js + Express API that uses JWT for authentication and provides simple banking endpoints.

## Features

- Register and login with JWT token issuance.
- Protected banking routes.
- Basic operations: balance, deposit, withdraw, transfer.
- In-memory storage for easy learning and quick setup.

## Quick Start

1. Install dependencies:

```bash
npm install
```

2. Create env file:

```bash
copy .env.example .env
```

3. Start server:

```bash
npm start
```

Server runs at `http://localhost:3000` by default.

## Authentication Endpoints

### Register

`POST /auth/register`

Body:

```json
{
  "username": "alice",
  "password": "alice123",
  "initialBalance": 1000
}
```

### Login

`POST /auth/login`

Body:

```json
{
  "username": "alice",
  "password": "alice123"
}
```

Both endpoints return:

```json
{
  "token": "<JWT>"
}
```

## Use JWT for Protected Endpoints

Add this header:

`Authorization: Bearer <JWT>`

## Banking Endpoints (Protected)

### Get Balance

`GET /api/balance`

### Deposit

`POST /api/deposit`

```json
{
  "amount": 250
}
```

### Withdraw

`POST /api/withdraw`

```json
{
  "amount": 120
}
```

### Transfer

`POST /api/transfer`

```json
{
  "toUsername": "bob",
  "amount": 80
}
```

## Notes

- Data is stored in memory and resets when server restarts.
- This is intentionally basic for learning and experimentation.