Signing up for Salient Data uses the GraphQL Resolver RootMutation `signUp()`,

This resolver is a member of the mutation family.

> GraphiQL Mutation

```
mutation {
  signUp(username: "{username}", password: "{password}", firstName: "{firstname}", lastName: "{lastname}")
  {
    _id
  }
}
```

The resulting data is:

```
{
  "data": {
    "signUp": {
      "_id": "5a6892724dad9a3321ad0632"
    }
  }
}
```

The token is what is used for the [Authorization](api-headers.md) header.

> Apollo Client Mutation

Apollo Client requires the mutation be formatted in the following method

    {
      mutation: gql`
        mutation signUp($username: String!, $password: String!, $firstName: String!, $lastName: String!) {
          signUp(username: $username, password: $password, firstName: $firstName, lastName: $lastName) {
            _id
          }
        }
      `,
      variables: {
        username: f.value.inputUserName,
        password: f.value.inputPassword,
        firstName: f.value.inputFirstName,
        lastName: f.value.inputLastName
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

    const signUp = {
      mutation: gql`
        mutation signUp($username: String!, $password: String!, $firstName: String!, $lastName: String!) {
          signUp(username: $username, password: $password, firstName: $firstName, lastName: $lastName) {
            _id
          }
        }
      `,
      variables: {
        username: f.value.inputUserName,
        password: f.value.inputPassword,
        firstName: f.value.inputFirstName,
        lastName: f.value.inputLastName
      },
    };

    this.apollo.mutate(signUp).subscribe(console.log);

 

