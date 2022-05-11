# Infonomic JavaScript Style Guide

JavaScript development at Infonomic mainly follows other 'best practice' guides and documentation - including the 'best parts' from the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) 

This style guide supplements other guides with current practices at Infonomic - not all of which are perfect, but will evolve over time. It's primarily designed to assist new developers in producing code and modules that will look familiar to everyone, making code easier to read, review, and maintain.

## Identifiers

For identifiers that contain acronyms, abbreviations, prefer all lower case if the acronym or abbreviation is at the start of the identifier, and all upper case if the acronym or abbreviation is within the identifier.

For example at the start of an identifier...

```js
    // prefer
    const nftHub = {}
    // over
    const NFTHub = {}
    // over
    const nFTHub = {}
```
Within an identifier...

```js
    // prefer
    const fetchNFT = {}
    // over
    const fetchNft = {}
```

```js
    // prefer
    const listNFTs = {}
    // over
    const listNfts = {}
```

An exception to the rule above is for identifiers that contain the ID abbreviation. In this case,

```js
    // prefer
    const tokenId = {}
    // over
    const tokenID = {}
```

## Field names (usually properties)

Database schemas at Infonomic use snake case - and all lower case. And so if you see identifiers or properties like the following, they usually represent data, via data transfer objects (DTOs)

```js
  const auction = {
    token_id: 1,
    nft_market: 'production',
    market_id: 1
    ...
  }

```

## GraphQL

The above is in contrast to GraphQL entities and return objects, which use Camel case, and follow the identifier rules above. For example...

```json
  {
    "id": "0x5dd1590a8b22facd1c10e6139743a238502dcda8-0x1",
    "auctionId": "1",
    "nft": {
      "id": "0xe9b9497798b5fe949039c01b1a772bdcb7e9ba10/0x18c4",
      "tokenId": "6340",
      "contract": {
        "id": "0xe9b9497798b5fe949039c01b1a772bdcb7e9ba10"
      }
    },
    "seller": {
      "id": "0x2bba82aa6364e583843f56f16ac98ead220b9732"
    },
    "duration": "86400",
    "status": "Finalized",
    "highestBid": {
      "bidder": {
        "id": "0x85176b04a01f2e2838eaa893b67e1bb40aa8db5d"
      },
      "amount": "5000000000000000000000"
    },

```


