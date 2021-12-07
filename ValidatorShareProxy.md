# ValidatorShareProxy

### Type Fields
```
type ValidatorShareProxy {
  contractAddress: Bytes!
  validatorId: BigInt!
}

type ValidatorShareProxyEvent {
  id: ID!
  contractAddress: Bytes!
  validatorId: BigInt!
  VFROM: Bytes!
  VTO: Bytes!
  VVALUE: BigInt!
  blockNumber: BigInt!
  blockHash: Bytes!
  transactionHash: Bytes!
  timestamp: BigInt!
}
```

### Enumeration
```
enum ValidatorShareProxy_orderBy {
  validatorId
}

enum ValidatorShareProxyEvent_orderBy {
  id
  validatorId
  blockNumber
  timestamp
}
```


### Input
```
input ValidatorShareProxy_filter {
  contractAddress: Bytes
  contractAddress_not: Bytes
  contractAddress_in: [Bytes!]
  contractAddress_not_in: [Bytes!]

  validatorId: BigInt
  validatorId_not: BigInt
  validatorId_gt: BigInt
  validatorId_lt: BigInt
  validatorId_gte: BigInt
  validatorId_lte: BigInt
  validatorId_in: [BigInt!]
  validatorId_not_in: [BigInt!]
}

input ValidatorShareProxyEvent_filter {
  id: ID
  id_not: ID
  id_in: [ID!]
  id_not_in: [ID!]

  contractAddress: Bytes
  contractAddress_not: Bytes
  contractAddress_in: [Bytes!]
  contractAddress_not_in: [Bytes!]

  validatorId: BigInt
  validatorId_not: BigInt
  validatorId_gt: BigInt
  validatorId_lt: BigInt
  validatorId_gte: BigInt
  validatorId_lte: BigInt
  validatorId_in: [BigInt!]
  validatorId_not_in: [BigInt!]

  VFROM: Bytes
  VFROM_not: Bytes
  VFROM_in: [Bytes!]
  VFROM_not_in: [Bytes!]

  VTO: Bytes
  VTO_not: Bytes
  VTO_in: [Bytes!]
  VTO_not_in: [Bytes!]

  blockNumber: BigInt
  blockNumber_not: BigInt
  blockNumber_gt: BigInt
  blockNumber_lt: BigInt
  blockNumber_gte: BigInt
  blockNumber_lte: BigInt
  blockNumber_in: [BigInt!]
  blockNumber_not_in: [BigInt!]

  blockHash: Bytes
  blockHash_not: Bytes
  blockHash_in: [Bytes!]
  blockHash_not_in: [Bytes!]

  transactionHash: Bytes
  transactionHash_not: Bytes
  transactionHash_in: [Bytes!]
  transactionHash_not_in: [Bytes!]

  timestamp: BigInt
  timestamp_not: BigInt
  timestamp_gt: BigInt
  timestamp_lt: BigInt
  timestamp_gte: BigInt
  timestamp_lte: BigInt
  timestamp_in: [BigInt!]
  timestamp_not_in: [BigInt!]
}
```

### Query Define
```
type Query {

  ...

  validatorShareProxies(
    skip: Int = 0
    first: Int = 100
    orderBy: ValidatorShareProxy_orderBy
    orderDirection: OrderDirection
    where: ValidatorShareProxy_filter
  ): [ValidatorShareProxy!]!

  validatorShareProxyEvent(
    id: ID!

  ): ValidatorShareProxyEvent
  validatorShareProxyEvents(
    skip: Int = 0
    first: Int = 100
    orderBy: ValidatorShareProxyEvent_orderBy
    orderDirection: OrderDirection
    where: ValidatorShareProxyEvent_filter
  ): [ValidatorShareProxyEvent!]!
}
```

### Example Query
```
{
  validatorShareProxies(
    first:10,
    orderBy:validatorId,
    orderDirection:desc,
    where:{validatorId:131}
  ){
    
    contractAddress
    validatorId
  }

  validatorShareProxyEvents(
    first: 10
    orderBy: timestamp
    orderDirection:desc
    where:{
      contractAddress:"0x8f846c443cfa44a6e95aacd2ac362b6cf4fd4335"
    }
  ){
    id
    contractAddress
    validatorId
    VFROM
    VTO
    VVALUE
    blockNumber
    blockHash
    transactionHash
    timestamp
  }

  transactions:validatorShareProxyEvents(
    first:10,
    orderBy:timestamp
    orderDirection:desc
    where:{
      timestamp_gt:1621391380,
      timestamp_lt:1622849915
    }
  ){
    transactionHash
    blockNumber
    timestamp
    VFROM
    VTO
    VVALUE
  }
  
  transactions_1:validatorShareProxyEvents(
    first:10,
    orderBy:timestamp
    orderDirection:desc
    where:{
      VTO: "0x0c10e3a179c8e9552fbba82950eed6f6161d7004"
    }
  ){
    transactionHash
    blockNumber
    timestamp
  }
}
```

### Full Schema
check [schema.graphql](https://github.com/furaprotocol/polygon-info/blob/main/schema.graphql)


### Use Playground
https://github.com/graphql/graphql-playground
