**Channels**

There are 5 transaction types: 2 that need to be signed by both:
channel_new, channel_team_close and 3 that are signed by one:
channel_solo_close, channel_slash, channel_timeout.

| Type | Transactions       | Signing                    |
|:-----|:-------------------|:---------------------------|
| 1    | channel_new        | need to be signed by both* |
| 2    | channel_team_close | need to be signed by both* |
| -    | -------            | -------                    |
| 3    | channel_solo_close | signed by one*             |
| 4    | channel_slash      | signed by one*             |
| 5    | channel_timeout    | signed by one*             |
|      |                    |                            |


**Need to be signed by both parties**

If your partner disappears, and you want to close the channel then you
first publish a solo_close, which gives the current state of the channel
which is defined by a turing complete contract that outputs a nonce.

The contract is split into _2 parts_ the _scriptpubkey part_ which both
participants signed and the _scripsig part_ which only one signed.

| Part | Name         | Signing           |
|:-----|:-------------|:------------------|
| 1    | scriptpubkey | signed by **two** |
| 2    | scripsig     | signed by **one** |

There is a third part that goes in the middle. The blockchain looks
things up in the merkel tree and provides that data to the smart
contract too. This is useful if you are betting on the outcome of
something in the oracle.


**signed by one party**

If your partner sees you publish a **channel_solo_close** that doesn't
output the highest nonce possible then they can do a **channel_slash**
transaction that outputs a higher nonce and this becomes the final state
that the channel gets closed at.

If your partner doesn't **slash** you, then eventually you can do a
**channel_timeout** transaction which closes the channel at the state
from the **channel_solo_close**.

| No. | recorded data on Blockchain               |
|:----|:------------------------------------------|
| 1.  | amount of money at the channel            |
| 2.  | the accound id's that control the channel |

The data that gets recorded on-chain for each channel is: How much money
is in the channel. The 2 accounts ids that control the channel.

***
[Zack’s - TOC Aeternity Blockchain Documentation](Zack_Docs_TOC)