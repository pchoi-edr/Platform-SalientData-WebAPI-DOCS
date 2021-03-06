Logging into Salient Data uses the GraphQL Resolver RootMutation `logIn()`,

This resolver is a member of the mutation family.

> GraphiQL Mutation

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

The resulting data is:

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

> Apollo Client Mutation

Apollo Client requires the mutation be formatted in the following method

    {
      mutation: gql`
        mutation logIn($username: String!, $password: String!) {
          logIn(username: $username, password: $password) {
            _id
          }
        }
      `,
      variables: {
        username: form.value.inputUserName,
        password: form.value.inputPassword
      },
    }

Apollo Client has several dependencies , which includes the `graphql-tag`

In the client, the following code would be used.

    import { Apollo } from 'apollo-angular';
    import gql from 'graphql-tag';

    class LogIn { ... }

    constructor(
      private apollo: Apollo
    ) {}

    const logIn = {
      mutation: gql`
        mutation logIn($username: String!, $password: String!) {
          logIn(username: $username, password: $password) {
            _id
          }
        }
      `,
      variables: {
        username: form.value.inputUserName,
        password: form.value.inputPassword
      },
    };

    this.apollo.mutate(logIn).subscribe(console.log);

 

