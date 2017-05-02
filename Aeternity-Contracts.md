# How contracts work

On æternity, smart contracts exist only inside off chain state channels. Just in case of disagreement between the parties the smart contract code gets enforced by the æternity blockchain. The blockchain here acts as a real world court who will only look int contracts on which the contracting parties disagree. The rest of the contracts are executed off-chain, ensuring fast and private execution.

# Contract components and participants

### Aeon: 

The use of the blockchain is not free, but requires that the user spends a token called aeon. Aeon are used as payment for any resources one consumes on the platform, as well as the basis for financial applications implemented on the platform.

### Accounts:

Each account has an address and a balance of aeon and also a nonce which increases with every transaction and the height of its last update. Each account 2 also has to pay a small fee for the amount of time it is open. The costs of creating and keeping accounts prevents spam and disincentives state-bloat. The reward for deleting accounts incentives the reclaiming of space.

### Name system: 

Many blockchain systems suffer from unreadable addresses for their users. In the vein of Aaron Swartz’ work and Namecoin, Æternity features a name system that is both decentralized and secure, while still supporting human-friendly names [9]. The blockchain’s state includes a mapping from unique human-friendly strings to fixed-size byte arrays. These names can be used to point to things such as account addresses on Æternity, or hashes e.g. of Merkle trees.

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

The hash of the previous block is required to maintain an ordering of the blockchain. The transaction tree contains all transactions that are included in the current block. With the exception of the consensus vote tree, all the trees are fully under consensus: if a tree is changed from one block to the next, this change has to be due to a transaction in the new block’s transaction tree, and a Merkle proof of the update has to be included in the block’s proof tree. The purpose of the three remaining trees will hopefully become clear in the following sections.

# Contracts interaction

Even though all contracts are stateless and execute independently of each other, contract interaction and statefulness can still be achieved through a the simple hashlocking operation. [(White Paper)(http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) This function can be used to predicate
the execution of code branches in different contracts on the existence of the same secret value. As a simple example usage, hashlocks make it possible for users that don’t share a state channel between them, to trustlessly send each other aeon, as long as there is a path of channels between them.


# How & when are contracts executed?

Contract execution is metered in a way similar to Ethereum’s “gas”, but æternity uses two different resources for its metering, one for time and one for space. Both of these resources are paid for using aeon (AE) by the party that requests the execution. This could be seen as undesirable, because it is probably another party that is causing the need for the blockchain to resolve the dispute in the first place. However, as long as all money in the channel is not used for betting, this can be effectively nullified in the contract code, since it has the ability to redistribute funds from one party to the other. It is in fact generally good practice to avoid using all funds in a channel to transact, because it disincentives the losing party to cooperate when closing the channel

# Writing a contract:
Documentation to syntax and sample common code.

[(White Paper)(http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) 

A reasonable future direction would be to experiment with high-level languages that adhere more closely to the functional paradigm. Keeping track of an implicit stack is generally error-prone and arguably not suitable for a high-level, developer-facing language. This should be rather easy given that programs are already pure functions (modulo some environment variables), and would greatly simplify both development and formal verification of contracts. If this is done, it could also make sense to revise the Virtual Machine (VM) to be tightly coupled with the new language, to make the compilation less error-prone and less dependent on trust in the developers. Ideally, the translation from surface language to VM code would simply be a direct transcription of peer-reviewed research, though pragmatic concessions will likely have to be made.

# Executing a contract: 
Documentation on submitting code to chain or running code of chain. Retrieving, triggering and updating state.