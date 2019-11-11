# graphql-ap

$ mkdir ap-server
$ cd ap-server
$ touch index.js
$ npm init -y

$ npm i apollo-server graphql

index.js
```js
const { ApolloServer, gql } = require('apollo-server');
const typeDefs = gql`
  type Query {
    ping: String
  }
`;

const server = new ApolloServer({
  typeDefs,
  resolvers
});

server.listen().then(({ url }) => {
  console.log(`Listening at ${url}`);
});
```


```node.js
node .

```


콘솔에 다음과 같이 curl 명령어를 통해 GraphQL Endpoint에 ping 
쿼리를 서버에 전송하면 응답 결과를 확인할 수 있습니다.

```
$ curl -X POST "http://localhost:4000/" -H "content-type: application/json" -d '{"query":"{ping}"}'
{"data":{"ping":"pong"}}
```
