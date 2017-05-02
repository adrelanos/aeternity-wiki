# How contracts work

On æternity, smart contracts exist only inside off chain state channels. Just in case of disagreement between the parties the smart contract code gets enforced by the æternity blockchain. The blockchain here acts as a real world court who will only look int contracts on which the contracting parties disagree. The rest of the contracts are executed off-chain, ensuring fast and private execution.

# Contract components and participants


# How & when are contracts executed?
# Writing a contract:
Documentation to syntax and sample common code.
(Source: White paper)

A reasonable future direction would be to experiment with high-level languages that adhere more closely to the functional paradigm. Keeping track of an implicit stack is generally error-prone and arguably not suitable for a high-level, developer-facing language. This should be rather easy given that programs are already pure functions (modulo some environment variables), and would greatly simplify both development and formal verification of contracts. If this is done, it could also make sense to revise the Virtual Machine (VM) to be tightly coupled with the new language, to make the compilation less error-prone and less dependent on trust in the developers. Ideally, the translation from surface language to VM code would simply be a direct transcription of peer-reviewed research, though pragmatic concessions will likely have to be made.

# Executing a contract: 
Documentation on submitting code to chain or running code of chain. Retrieving, triggering and updating state.