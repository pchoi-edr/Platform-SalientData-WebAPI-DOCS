# GraphQL Schemas

> Banks

```
enum Banks {
  WELLSFARGO
  BANKOFAMERICA
  OTHER
}
```

> Status

```
enum Status {
  SUBMITTED
  PENDING
  PROCESSING
  PROCESSED
}
```

> User

```
type User {
  _id: String! 
  firstName: String
  lastName: String
  username: String!
  salientPosts: [Post] 
  salientData: [Salient]
}
```

> Auth Token

```
type AuthPayload {
  token: String # JSON Web Token
  data: User
}
```

> Salient Post

```
type Post {
  _id: String!
  title: String!
  bank: String
  summary: String
  content: String!
  createdAt: String
  comments(limit: Int) : [Comment]
  salients(limit: Int) : [Salient]
  vendor: User
}
```

> Salient Data

```
type SalientData {
  _id: String!
  data: String
  createdAt: String
  salientId: String!
  vendor: User
}
```

`This schema is non accessible by the resolvers as it is used by the API to convert and store the data into document format.`

#### Input Schemas

> Salient Post

```
input salientInput {
  title: String!
  content: String!
  summary: String
  bank: Banks
}
```

> Salient Data

```
input salientDataInput {
  data: String!
  salientId: String!
}
```

`This schema is non accessible by the resolvers as it is used by the API to convert and store the data into document format.`

#### Root Queries

```
type RootQuery {
  viewer: User
  vendor(username: String!): User
  vendors: [User]
  salientPosts(bank: Banks): [Post]
  salient(_id: String!) : Post
  salientData(_id: String) : Post
}
```

#### Root Mutations

```
type RootMutation {
  signUp (
    username: String!
    password: String!
    firstName: String
    lastName: String
  ): User
  
  logIn (
    username: String!
    password: String!
  ): AuthPayload

  createPost (
    salient: salientInput
  ): Post
  
  createComment (
    salientId: String!
    content: String!
  ): Comment
  
  removePost (
    _id: String! 
  ): Post
  
  removeComment (
    _id: String! 
  ): Comment
  
  createSalientData (
    salientData: salientDataInput
  ): Salient
  
  removeSalientData (
    _id: String! 
  ): Salient
  
}
```



