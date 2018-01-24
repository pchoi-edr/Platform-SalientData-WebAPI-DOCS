# Submit Salient Data

Logging into Salient Data uses the GraphQL Resolver RootMutation `createPost()`.

This resolver is a member of the mutation family.

> GraphiQL Mutation

```
mutation {
  createPost(salient: {
    title: "{title}",
    content: "{salient-data}",
    summary: "{description}",
    bank: WELLSFARGO
  })
  { 
    _id
    title
  }
}
```

The resulting data is:

```
{
  "data": {
    "createPost": {
      "_id": "5a6896734dad9a3321ad0633",
      "title": "{title}"
    }
  }
}
```

The field `bank` is an enumeration of bank names predefined.

```
enum Banks {
  WELLSFARGO
  BANKOFAMERICA
  { ... }
  OTHER
}
```

> Apollo Client Mutation

Apollo Client requires the mutation be formatted in the following method

    {
      mutation: gql`
        mutation createPost($title: String!, $content: String!, $salient: String!, $bank: String!) {
          createPost(salient: {
            title: "$title}",
            content: "$salient",
            summary: "$summary",
            bank: $bank
          })
          { 
            _id
            title
          }
        }
      `,
      variables: {
        title: f.value.title,
        salient: JSON.stringify(f.value.content),
        summary: f.value.summary,
        bank: f.value.bank
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



