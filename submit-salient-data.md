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

`Because we are working with RESTful API's, all salient data, whether xml or JSON must be stringified before submitting.`

Apollo Client has several dependencies , which includes the `graphql-tag`

In the client, the following code would be used.

    import { Apollo } from 'apollo-angular';
    import gql from 'graphql-tag';

    class LogIn { ... }

    constructor(
      private apollo: Apollo
    ) {}

    const post = {
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
    };

    this.apollo.mutate(post).subscribe(console.log);



