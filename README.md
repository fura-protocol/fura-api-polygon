# Polygon Info

### Fura - Polygon Info GraphQL Endpoint
https://api.fura.org/subgraphs/name/polygon

## Code Configuration

### 1. Query:

#### Example
```
export const client = new ApolloClient({
  link: new HttpLink({
    uri: 'https://api.fura.org/subgraphs/name/polygon',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})
```

### 2. Subscription:

#### WebSocket Secure Endpoint

```
wss://api.fura.org/subgraphs/name/polygon
```

WebSocket protocols are currently supported, both with [subscriptions-transport-ws](https://github.com/apollographql/subscriptions-transport-ws) and [graphql-ws](https://github.com/enisdenjo/graphql-ws)  

https://github.com/apollographql/subscriptions-transport-ws/blob/master/PROTOCOL.md  

https://github.com/enisdenjo/graphql-ws/blob/master/PROTOCOL.md

Check links above for more details  

#### Example

```
import { SubscriptionClient } from 'subscriptions-transport-ws';
import ApolloClient from 'apollo-client';

const GRAPHQL_ENDPOINT = 'wss://api.fura.org/subgraphs/name/polygon';

const client = new SubscriptionClient(GRAPHQL_ENDPOINT, {
  reconnect: true,
});

const apolloClient = new ApolloClient({
    networkInterface: client,
});
```

## CORS Settings
https://api.fura.org/subgraphs/name/polygon 

now supports:
```
localhost:3000
localhost:9528
127.0.0.1:3000
127.0.0.1:9528
wallet.polygon.technology
polygon.technology
```

## Full Schema
check [schema.graphql](https://github.com/fura-protocol/fura-api-polygon/blob/main/schema.graphql)


## Use Playground
https://github.com/graphql/graphql-playground  

https://github.com/graphql/graphiql

