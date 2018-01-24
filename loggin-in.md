# Logging In

#### Logging into Salient Data

Logging into Salient Data uses the GraphQL Resolver `logIn()`,

This resolver is a member of the mutation family.

```
mutation {
  logIn(username: "{username}", password: "{password}") {
    token
    data {
      _id
    }
  }
}
```

The resulting result is:

```
{
  "data": {
    "logIn": {
      "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJfaWQiOiI1YTNmYzk5MWJkMWE2ODBmZDliMTE4ZGEiLCJpYXQiOjE1MTY3NzkxMjYsImV4cCI6MTUxNjg2NTUyNiwiaXNzIjoiZmVhdGhlcnMifQ.pB2qdyns8E-RZWXo5AxtCGqGzkHu4Exq3OwjItn7Z24",
      "data": {
        "_id": "5a3fc991bd1a680fd9b118da"
      }
    }
  }
}
```

The token is what is used for the [Authorization](api-headers.md) header.