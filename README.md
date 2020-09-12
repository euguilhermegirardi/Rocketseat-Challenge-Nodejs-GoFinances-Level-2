<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios-new.png" />

<h3 align="center">
  Desafio 05: GoFinances - Node.js
</h3>

<blockquote align="center">“For those who get better every day, getting ready is utopia”!</blockquote>

## :rocket: About the challenge

In this challenge, you must create an application to continue training what you have learned so far in Node.js with TypeScript, using the concept of models, repositories and services!

This will be an application to store incoming and outgoing financial transactions, which should allow the registration and listing of these transactions.

### Rotas da aplicação

Now that you have the template cloned, and ready to continue, you should check the files in the src folder and complete where there is no code with the code to achieve the objectives of each route.

- **`POST /transactions`**: The route must receive title, value and type within the body of the request, type is the type of the transaction, which must be income for inflows (deposits) and outcome for outflows (withdrawals). When registering a new transaction, it must be stored inside an object with the following format:

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income"
}
```

- **`GET /transactions`**: 
This route should return a listing with all the transactions you have registered so far, together with the sum of the entries, withdrawals and total credit. This route must return an object with the following format:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

### Especificação dos testes

In each test, you have a brief description of what your application must do in order for the test to pass.

For this challenge we have the following tests:

- **`should be able to create a new transaction`**: For this test to pass, your application must allow a transaction to be created, and return a json with the created transaction.

- **`should be able to list the transactions`**: For this test to pass, your application must allow an object to be returned containing all transactions along with the balance of income, outcome and total transactions that have been created so far.

- **`should not be able to create outcome transaction without a valid balance`**: For this test to pass, your application must not allow a transaction of the `outcome` type to exceed the total amount the user has in the box, returning a response with HTTP 400 code and an error message in the following format:` {error: string} `
