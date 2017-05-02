# How contracts work

On æternity, smart contracts exist only inside off chain state channels. Just in case of disagreement between the parties the smart contract code gets enforced by the æternity blockchain. The blockchain here acts as a real world court who will only look int contracts on which the contracting parties disagree. The rest of the contracts are executed off-chain, ensuring fast and private execution.

# Contract components and participants

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