# Bunk Dev Test - Holiday Expenses Calculator

A code challenge for new developers applying to work at Bunk.

## Challenge

The Bunk team are all going on a work holiday but they need an app to keep a track of expenses and who owes money to who at the end of the trip.

## Technologies Used

- TypeScript preferably, (JavaScript if not familiar with TypeScript)
- Angular 15+
- Node 16+ + Web Framework, i.e. Express
- Backend tests (ideally with Jest)
- E2E tests (ideally with Cypress)
- Git + Github for version control


## Installation

Run `npm run install-all` in the project root.

This script will kick off `npm install` in both the Express server (`api`) and the Angular application (`web`).

## Quick Start

Run `npm run start` from the project root. This script will start both the Express server, and the Angular application.

## Running Tests

For tests execution Run `npm run test` in the project root.

## API Reference

### Calculate Payouts (`POST /payouts`)

**Endpoint URL**
`http://localhost:3000/payouts`

**JSON Body Parameters**

`expenses` - array : Specifies the expenses you want to calculate a payout on.

`expenses.name` - string : The name of the person who incurred the expense.

`expenses.amount` - number : The amount of the expense incurred.

**Example Request**

```shell script
curl --location --request POST 'localhost:3000/payouts' \
--header 'Content-Type: application/json' \
--data-raw '{
	"expenses": [
		{ "name": "Adriana", "amount": 5.75 },
		{ "name": "Adriana", "amount": 5.75 },
		{ "name": "Bao", "amount": 12 }
	]
}'
```

**Example Response**

```json
{
  "total": 23.5,
  "equalShare": 11.75,
  "payouts": [
    {
      "owes": "Adriana",
      "owed": "Bao",
      "amount": 0.25
    }
  ]
}
```
## Developer Comment

I have completed the test task using Angular and Express, few test cases are also written at both frontend and backend using specified technologies.
