# Polygon Staking

### Fura - Polygon Staking GraphQL Endpoint
https://polygon.furadao.org/subgraphs/name/staking

### Code Configuration

```
export const client = new ApolloClient({
  link: new HttpLink({
    uri: 'https://polygon.furadao.org/subgraphs/name/staking',
  }),
  cache: new InMemoryCache(),
  shouldBatch: true,
})
```

### CORS Settings
https://polygon.furadao.org/subgraphs/name/staking 

now supports:
```
localhost:3000
localhost:9528
127.0.0.1:3000
127.0.0.1:9528
wallet.polygon.technology
```

### Full Schema
check [schema.graphql](https://github.com/furaprotocol/polygon-staking-info/blob/main/schema.graphql)


### Use Playground
https://github.com/graphql/graphql-playground

