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
Within and identifier...

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

