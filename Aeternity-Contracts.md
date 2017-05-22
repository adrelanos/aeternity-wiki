# How do contracts work

On the æternity network, smart contracts only exist in off-chain state channels. In case of disagreement between the parties in the channel, the smart contract code gets enforced by the æternity blockchain. In essence, the underlying blockchain acts to enforce and mitigate any disagreements between contracting parties in a transaction. The rest of the contracts are executed off-chain, ensuring fast and private execution.

# Contract components and participants

### Aeon: 

The use of the blockchain is not free but requires the user to spend tokens called AEON. Aeon is used as payment for any resources one consumes on the platform, as well as the basis for financial applications implemented on the platform.

### Accounts:

Each account has an address, Aeon balance,  and nonce that increases with every transaction and the height of the last update. Each account also accrues a small fee relative to the amount of a time that it is open. The costs of creating and keeping accounts open prevents spam and disincentivizes state-bloat. Reward for deleting accounts incentivizes the reclaiming of space.

### Name system: 

Many blockchain systems suffer from unreadable addresses for their users. In the vein of Aaron Swartz’ work and [Namecoin](https://namecoin.org), æternity features a naming system that is both decentralized and secure, while still supporting human-friendly names. The blockchain’s state includes a mapping from unique human-friendly strings to fixed-size byte arrays. These names can be used to point to things such as account addresses on æternity, or hashes e.g. of Merkle trees.

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

The hash of the previous block is required to maintain an ordering of the blockchain. The transaction tree contains all transactions that are included in the current block. If any tree is changed from one block to the next, this change has to be due to a transaction in the new block’s transaction tree and must include a Merkle proof of the update that can be found in the block’s proof tree. With the exception of the consensus vote tree, all the Merkle trees are characterized by this consensus method.  The purpose of the three remaining trees is detailed in the following sections.

### State channels:

On æternity, the only state update that can be settled on the blockchain is a transfer of Aeon, and the only Aeon that can be transferred are the ones that the transacting parties already deposited into the channel. This makes all channels
independent from each other, and results in the immediate benefit that any channel-related transactions can be processed in parallel. This greatly improves transaction throughput.

The blockchain is only used to settle the final outcome or to resolve conflicts that arise, roughly analogous to the judicial system. However, because the blockchain’s behavior will be predictable, there is no gain in disputing the intended result of a state channel; malicious actors are incentivized to behave correctly and only settle the final state on the blockchain. All taken together, this increases transaction speed and volume by several orders of magnitude, while contributing to increased privacy.

### Smart contracts:

Despite how on-chain state settlement is limited to the transfer of Aeon, æternity still features a Turing-complete virtual machine that can run “smart contracts”. Contracts on æternity are strictly agreements that distribute funds according to some rules. This stands in stark contrast to the entity-like contracts of e.g. Ethereum. Two of the more notable practical differences are that, by default, only the involved parties know about a given contract and only parties that have an open state channel can create a valid contract. If the parties agree to a contract, they sign it and keep copies for future reference. It is only submitted to the blockchain if its outcome is disputed, in which case the code is only ever stored as part of the submitted transaction, never in any other state. If this happens, the blockchain distributes the tokens according to the contract and closes the channel.

# Contracts interaction

Even though all contracts are stateless and execute independently of each other, contract interaction and statefulness can still be achieved through a simple hash locking operation. [(White Paper)](http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) This function can be used to predicate
the execution of code branches in different contracts on the existence of the same secret value. A simple usage example is how hashlocks make it possible for users to trustlessly send each other Aeon as long as there is a path of channels between them: even when they don’t share the same state channel.


# How & when are contracts executed?

Contract execution is metered in a way similar to Ethereum’s “gas”, but æternity uses two different resources for its metering, one for time and one for space. Both of these resources are paid for using Aeon (AE) by the party that requests the execution. This could be seen as undesirable because it is probably another party that is causing the need for the blockchain to resolve the dispute in the first place. However, as long as all money in the channel is not used for betting, this can be effectively nullified in the contract code, since it has the ability to redistribute funds from one party to the other. It is in fact generally good practice to avoid using all funds in a channel to transact because it disincentivizes the losing party to cooperate when closing the channel.

# Writing a contract:
Documentation to syntax and sample common code.

[(White Paper)](http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) 

A reasonable future direction would be to experiment with high-level languages that adhere more closely to the functional paradigm. Keeping track of an implicit stack is generally error-prone and, arguably, it is not suitable for a high-level, developer-facing language. Working in this future direction should be rather easy given that programs are already pure functions (modulo some environment variables), and would greatly simplify both development and formal verification of contracts. If this is done, it could also make sense to revise the Virtual Machine (VM) to be tightly coupled with the new language, to make the compilation less error-prone and less dependent on trust in the developers. Ideally, the translation from surface language to VM code would simply be a direct transcription of peer-reviewed research, though pragmatic concessions will likely have to be made.

# Executing a contract: 
Documentation on submitting code to chain or running code of chain. Retrieving, triggering and updating state.

***
related: [Terminal-interface-commands](Terminal-interface-commands#contracts)