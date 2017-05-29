# How do contracts work?

On the æternity Blockchain, smart contracts only exist in off-chain state channels. Transactions flow directly between the parties in the channels. The Blockchain only intervenes in case of disagreement between the parties in the channel. At this point the Blockchain searches for the latest state signed by all parties and enforces the smart-contract code at that state. In essence, the underlying Blockchain acts  as a crypto-court that mitigates disagreements between contracting parties in a transaction. The rest of the contracts are executed off-chain, ensuring fast and private execution.

# Contract components and participants

### æon: 

The use of the Blockchain is not free but requires the user to spend tokens called æon. They are used as payment for any resources (computation time or storage space) one consumes on the platform through the execution of transaction or smart-contact codes. æons are also the basis for all financial applications implemented on top of the platform.

### Accounts:

Each account has an address, æon balance,  and nonce that increases with every transaction and the height of the last updated block on the Blockchain. Each account also accrues a small fee relative to the amount of a time that it is open. The costs of creating and keeping accounts open prevents spam and disincentivises state-bloat. In contrast, the reward for deleting accounts incentivises the reclaiming of space on the Blockchain. These measures will enforce a good use of storage space on the Blockchain, which in turn will yield better usability, and more efficiency.

### Name system: 

Many blockchain systems suffer from unreadable addresses for their users. In the vein of Aaron Swartz’ work and [Namecoin](https://namecoin.org), æternity features a naming system that is both decentralized and secure, while still supporting human-friendly names. The Blockchain’s state includes a mapping from unique human-friendly strings to fixed-size byte arrays. These names can be used to point to things such as account addresses on æternity, or hashes e.g. of Merkle trees.

### Block contents: 

Each block contains the following components:

• The hash of the previous block.

• A Merkle tree of transactions.

• A Merkle tree of accounts.

• A Merkle tree of names.

• A Merkle tree of open channels.

• A Merkle tree of oracles which haven’t answered their respective questions.

• A Merkle tree of oracle answers.

• A Merkle tree of Merkle proofs.

• The current entropy in the random number generator.

The hash of the previous block is required to maintain a correct ordering of the Blockchain. The transaction tree contains all transactions that are included in the current block. If any tree is changed from one block to the next, this change has to be due to a transaction in the new block’s transaction tree and must include a Merkle proof of the update that can be found in the block’s proof tree. With the exception of the consensus vote tree, all the Merkle trees are characterized by this consensus method.

### State channels:

On æternity, the only state update that can be settled on the Blockchain is a transfer of æon, and the only æon that can be transferred are the ones that the transacting parties already deposited into the channel. This makes all channels
independent from each other, and results in the immediate benefit that any channel-related transactions can be processed in parallel. This greatly improves transaction throughput.

The Blockchain is only used to settle the final outcome or to resolve conflicts that arise, roughly analogous to the judicial system. However, because the Blockchain’s behavior will be predictable, there is no gain in disputing the intended result of a state channel; malicious actors are incentivised to behave correctly and only settle the final state on the Blockchain. All taken together, this increases transaction speed and volume by several orders of magnitude, while contributing to increased privacy.

### Smart contracts:

Despite how on-chain state settlement is limited to the transfer of Aeon, æternity still features a Turing-complete virtual machine that can run “smart contracts”. Contracts on æternity are strictly agreements that distribute funds according to some rules. This stands in stark contrast to the entity-like contracts of e.g. Ethereum. Two of the more notable practical differences are that, by default, only the involved parties know about a given contract and only parties that have an open state channel can create a valid contract. If the parties agree to a contract, they sign it and keep copies for future reference. It is only submitted to the blockchain if its outcome is disputed, in which case the code is only ever stored as part of the submitted transaction, never in any other state. If this happens, the blockchain distributes the tokens according to the contract and closes the channel.

# Contract interaction

Even though all contracts are stateless and execute independently of each other, contract interaction and statefulness can still be achieved through a simple hash locking operation. [(White Paper)](https://github.com/aeternity/wiki/blob/master/whitepapers/%C3%A6ternity-blockchain-whitepaper.pdf) This function can be used to predicate the execution of code branches in different contracts on the basis of existence of the same secret value. A simple usage example would be to use these hashlocks to make it possible for users to trustlessly send each other æon as long as there is a path of channels between them: even when they don’t share the same state channel. Another implementation would be the cross-chain atomic swaps.

# How and when are contracts executed?

Contract execution is metered in a way similar to Ethereum’s “gas”, but æternity uses two different resources for its metering, one for time and one for space. Both of these resources are paid for using æon (AE) by the party that requests the execution. This could be seen as undesirable because it is probably another party that is causing the need for the blockchain to resolve the dispute in the first place. However, as long as all money in the channel is not used for betting, this can be effectively nullified in the contract code, since it has the ability to redistribute funds from one party to the other. It is in fact generally good practice to avoid using all funds in a channel to transact because it disincentivises the losing party to cooperate when closing the channel.

# Writing a contract:
Documentation of syntax and samples of common code.

[(White Paper)](https://github.com/aeternity/wiki/blob/master/whitepapers/%C3%A6ternity-blockchain-whitepaper.pdf) 

A reasonable future direction would be to experiment with high-level languages that adhere more closely to the functional paradigm. Keeping track of an implicit stack is generally error-prone and, arguably, it is not suitable for a high-level, developer-facing language. Working in this future direction should be rather easy given that programs are already pure functions (modulo some environment variables), and would greatly simplify both development and formal verification of contracts. If this is done, it could also make sense to revise the Virtual Machine (VM) to be tightly coupled with the new language, to make the compilation less error-prone and less dependent on trust in the developers. Ideally, the translation from surface language to VM code would simply be a direct transcription of peer-reviewed research, though pragmatic concessions will likely have to be made.

# Executing a contract: 
Documentation on submitting code to chain or running code of chain. Retrieving, triggering and updating state.

***
related: [Terminal-interface-commands](Terminal-interface-commands#contracts)