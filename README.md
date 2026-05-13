# transactions-api
Transactions API
Node + Express + MongoDB + Dev Container + Heroku
A classroom-style project demonstrating how to build a simple REST API using:

Node.js
Express
MongoDB
Docker
VS Code Dev Containers
Heroku Deployment
Project Goal
Create a Transactions API for storing credit card transactions.

Transactions follow an append-only design:

Transactions are never edited
Transactions are never deleted
Corrections are done using amendment transactions
Data Model
Each transaction contains:

{
  "id": "...",
  "creditCardNickname": "Costco Visa",
  "cardType": "Visa",
  "date": "2026-05-12",
  "amount": 42.75,
  "amendment": false,
  "comment": "Gas"
}
Supported Card Types
Visa
Master
Amex
Discover
Other
API Endpoints
POST
Create a transaction:

POST /transactions
GET
Get all transactions:

GET /transactions
Get transaction by id:

GET /transactions/:id
Get transactions by date:

GET /transactions?date=YYYY-MM-DD
Get transactions by date range:

GET /transactions?startDate=YYYY-MM-DD&endDate=YYYY-MM-DD
Get transactions by credit card nickname:

GET /transactions?creditCardNickname=Costco Visa
Important Design Decision
This API intentionally DOES NOT support:

PUT
PATCH
DELETE
Financial records should not be destructively modified.

Instead:

Incorrect Transaction
        ↓
Create Amendment Transaction
