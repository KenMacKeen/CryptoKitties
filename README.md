CryptoKitty is one of the world's first blockchain games, allowing players to purchase, breed, and trade virtual cats with different visual features of varying levels of rarity. In December 2017, the game became so popular that it pushed the Ethereum network to an all-time high in the number of transactions and accounted for over 10% of network traffic. 

This is a crypto kitties application written in the solidity programming language and deployed on the Ethereum Sepolia testnet.

Contract Address: 0xe599488ff550166133bE62E54e44915df37c2a3e

# SimpleCryptoKitties
                                                                                                                          A Solidity smart contract implementation of a blockchain-based NFT cat breeding game, deployed on the Ethereum Sepolia
   testnet.

  ## Overview

  CryptoKitties was one of the world's first blockchain games, launching in December 2017 and at its peak accounting for
   over 10% of Ethereum's network traffic. This project is a simplified implementation of the core mechanics — minting,
  breeding, and tracking unique digital cats as ERC721 NFTs.

  ## Features

  - **ERC721 Compliant** — Each kitty is a standard NFT, fully transferable and tradeable
  - **Unique Genetics** — Every kitty has a `genes` value derived from block data, making each one distinct
  - **Breeding** — Owners can breed two of their kitties to produce offspring with blended genetics
  - **Generation Tracking** — Kitties record their generation, mom ID, dad ID, and birth time on-chain
  - **Genesis Kitties** — Two generation-0 kitties are created at deployment

  ## Contract

  | | |
  |---|---|
  | **Contract Name** | `SimpleCryptoKitties` |
  | **Token Symbol** | `SCK` |
  | **Network** | Ethereum Sepolia Testnet |
  | **Address** | [`0xe599488ff550166133bE62E54e44915df37c2a3e`](https://sepolia.etherscan.io/address/0xe599488ff5501661
  33bE62E54e44915df37c2a3e) |
  | **Solidity Version** | `0.8.17` |
  | **Standard** | OpenZeppelin ERC721 v4.9.3 |

  ## Data Structure

  Each kitty is stored as:

  ```solidity
  struct Kitty {
      uint256 genes;       // Unique genetic hash
      uint256 birthTime;   // Block timestamp at creation
      uint256 momId;       // Token ID of the mother (0 for gen-0)
      uint256 dadId;       // Token ID of the father (0 for gen-0)
      uint256 generation;  // Generation number
  }

  Key Functions

  breed(uint256 momId, uint256 dadId)

  Breed two kitties you own to produce a new offspring. The child's genes are derived from the parents' combined
  genetics, and its generation is set to max(mom.generation, dad.generation) + 1.

  Requirements: You must own both the mom and dad kitties.

  Usage

  Interact with the contract via
  https://sepolia.etherscan.io/address/0xe599488ff550166133bE62E54e44915df37c2a3e#writeContract using a wallet connected
   to the Sepolia testnet (e.g. MetaMask). You can call breed() directly from the Write Contract tab.

  Tech Stack

  - Solidity 0.8.17
  - OpenZeppelin ERC721 contracts 4.9.3
  - Ethereum Sepolia testnet
