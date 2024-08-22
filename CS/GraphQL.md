# GraphQL
GraphQL 은 한 문장으로 얘기하자면 페이스북에서 만든 API 를 위한 쿼리 언어이다.           
타입 시스템을 사용하여 쿼리를 실행하는 서버사이드 런타임이고,
특정 데이터베이스나 플랫폼에 종속적이지 않다.          
REST API 는 endpoint가 아주 다양하지만 GraphQL은 endpoint가 하나이다. GraphQL은 /graphql endpoint에 요청에 따라 쿼리를 조합해서 요청하면 되기 때문에 URL을 설계하고 만들어주지 않아도 된다.        
# GraphQL의 구조
REST API와 다르게 GraphQL은 클라이언트가 요청하는 데이터의 구조를 명확하게 정의할 수 있다.           
GraphQL 스키마는 API의 데이터 구조를 정의하는데 스키마에는 모든 가능한 쿼리, 뮤테이션, 그리고 반환할 데이터 타입이 명시되어 있다.        
```graphql
type Query {
  user(id: ID!): User
  posts: [Post]
}클라이언트가 필요한 데이터를 직접 지정할 수 있기 때문에

type User {
  id: ID!
  name: String!
  email: String
  posts: [Post]
}

type Post {
  id: ID!
  title: String!
  content: String!
  author: User
}
```
이런 식으로 REST API는 DTO 3개를 만들어 주어야 하지만 graphql은 클라이언트가 필요한 데이터를 직접 지정할 수 있기 때문에 많은 DTO를 만들 필요없이 단일 쿼리로 필요한 데이터만 요청할 수 있다.         
# 쿼리와 뮤테이션
GrahpQL 은 크게 쿼리(query) 와 뮤테이션(mutation)으로 나눌 수 있다.         
쿼리(query) 는 조회시 사용하고, 뮤테이션(mutatiton) 은 조회 외 수정 / 삭제 / 생성 에 사용된다.       
```graphql
query {
  user(id: "1") {
    name
    email
    posts {
      title
      content
    }
  }
}
---
mutation {
  createUser(name: "gunju", email: "gunju@gmail.com") {
    id
    name
    email
  }
}
```
