# Whisper Transaction for EthOnline 2024

## Short Description

Token Transfer on public chain using ZKP and privacy-preserving token

## Long Description

This project represents an implementation of private transactions on a public blockchain, specifically Hedera Hashgraph, using the Hyperledger Zeto toolkit. Here's a technical description of the project:

_Architecture_
The project combines Hedera Hashgraph's public distributed ledger with Hyperledger Zeto's privacy-preserving token toolkit to enable confidential token transfers between Hedera wallets. It leverages several key components:

1. The native token management on the Hedera network.
2. The deployment and execution of the privacy-preserving smart contracts.
3. Hyperledger Zeto: A UTXO-based privacy toolkit utilizing Zero Knowledge Proofs (ZKPs).

_Key Technical Features_
_*UTXO Model*_
Unlike typical ERC-20 tokens on Ethereum-compatible chains, this project adopts a UTXO (Unspent Transaction Output) model similar to Bitcoin. This approach enhances privacy and enables better parallel processing of transactions.

_*Zero Knowledge Proofs*_
The project extensively uses ZKPs to validate transactions without revealing sensitive information. The ZKP circuits support various levels of privacy, including:

- Anonymity for sender and receiver
- Confidentiality of transaction values
- Masking of transaction history

_*Commitment Scheme*_
Each UTXO is represented on-chain as a commitment hash, combining:

- Token value
- Salt (for randomness)
- Owner's public key

_Transaction Flow_

1. The sender creates a transaction, consuming one or more input UTXOs and creating new output UTXOs.
2. A ZKP is generated to prove the transaction's validity without revealing its details.
3. The transaction and proof are submitted to the Hedera Smart Contract Service.
4. The smart contract verifies the ZKP and, if valid, updates the on-chain state by nullifying input UTXOs and creating new output UTXOs.

_Privacy Levels_
Multiple level of privacy configuration is possible:

1. Basic anonymity with unencrypted values
2. Enhanced privacy with encrypted values
3. Full privacy with history masking using nullifiers

For this project, we have used Basic anonymity to demonstrate the concept.

_Integration with Hedera_

- The project utilizes Hedera's native token capabilities through the Hedera Token Service.
- Smart contracts are deployed using Hedera's Solidity-compatible environment, leveraging the Ethereum Virtual Machine (EVM).
- Transactions benefit from Hedera's high throughput and low, predictable fees.

_Unique Aspects_

1. First known implementation of UTXO-based private tokens on Hedera's public network.
2. Combines the security and efficiency of Hedera's hashgraph consensus with advanced cryptographic privacy techniques.
3. Demonstrates the potential for enterprise-grade privacy solutions on public ledgers, addressing a key concern for institutional adoption.

This project showcases the potential for building sophisticated, privacy-preserving decentralized applications on Hedera Hashgraph, bridging the gap between public blockchain transparency and the privacy requirements of sensitive financial transactions.

## How to run

Follow the instructions in each of the submodules:

- txn-app
- txn-backend
