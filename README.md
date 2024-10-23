# Personal Financial Manager API
A RESTful API for managing personal financial records, allowing users to record income and expenses, retrieve past transactions, and get summaries by category or time period.

Table of Contents
Features
Technologies
Installation
API Endpoints
Testing the API
Contributing

Features
Record income and expenses.
Retrieve all transactions.
Update existing transactions.
Delete transactions.
Get summaries of transactions by category or time period.

Technologies
Backend Framework: Node.js with Express.js
Database: SQLite (for simplicity)
Testing Tools: Postman, REST Client for Visual Studio Code

Installation

Clone the repository:

1.git clone https://github.com/devendratalari-22/finance-manager-api.git cd finance-manager-api

2.Install dependencies: npm install

3.Setup the database: If you are using SQLite, the database will be created automatically when you run the application.

4.Run the application: node app.js The server will start at http://localhost:3000.

API Endpoints

Transactions
GET /transactions: Retrieve all transactions.
POST /transactions: Add a new transaction.

Request Body:
json
{
    "type": "income", // or "expense"
    "category": "Salary",
    "amount": 5000,
    "date": "2024-10-21",
    "description": "October salary"
}
GET /transactions/: Retrieve a transaction by ID.

PUT /transactions/: Update a transaction by ID.
Request Body:
{
    "type": "income",
    "category": "Salary",
    "amount": 5500,
    "date": "2024-10-21",
    "description": "Updated October salary"
}
DELETE /transactions/: Delete a transaction by ID.

Summary
GET /summary: Retrieve a summary of transactions, including total income, total expenses, and balance. You can optionally filter by date range or category.

Testing the API You can test the API using Postman or by using the included .http file:

Create a file named apiRequests.http and include the following content:
GET all transactions
GET http://localhost:3000/transactions Accept: application/json

POST a new transaction
POST http://localhost:3000/transactions Content-Type: application/json

{ "type": "income", "category": "Salary", "amount": 5000, "date": "2024-10-21", "description": "October salary" }

PUT to update a transaction
PUT http://localhost:3000/transactions/1 Content-Type: application/json

{ "type": "income", "category": "Salary", "amount": 5500, "date": "2024-10-21", "description": "Updated October salary" }

DELETE a transaction
DELETE http://localhost:3000/transactions/1

Use a REST client (e.g., Postman or the REST Client extension in Visual Studio Code) to send the requests.

Contributing Contributions are welcome! Please open an issue or submit a pull request for any changes or improvements.

Fork the repository. Create your feature branch (git checkout -b feature-branch). Commit your changes (git commit -m 'Add some feature'). Push to the branch (git push origin feature-branch). Open a pull request.










