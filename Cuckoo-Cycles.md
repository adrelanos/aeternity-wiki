
## Introduction of Proof of Work

A proof of work(PoW) system allows for the checker to verify with
minimal effort that a proper has expended a large amount of
computational effort. Originally used for fighting spam, where a sender
has to expend a large amount of effort to demand the attention of a
recipient, now it is a cornerstone of crypto-currencies.

For example, Bitcoin uses Hashcash. Hashcash entails finding a nonce
value such that application of a cryptographic hash function to this
nonce and the rest of the block header, results in a number below a
target threshold. The threshold is dynamically adjusted by the protocol
so as to maintain an average block interval of 10 minutes.

Bitcoin’s choice of the simple and purely compute-bound SHA256 hash
function allowed for an easy migration of hash computation from desktop
processors (CPUs) to graphics-card processors (GPUs), to
field-programmable gate arrays (FPGAs), and finally to custom designed
chips (ASICs), with huge improvements in energy-efficiency at every
step.

However, there is a current problem with Hashcash, that individuals or
organizations can decide to invest heavily into mining bitcoin by buying
or fabricating ASICs that have high energy efficiency and superior hash
computation speed, thereby making up most of the hash power. Since
Bitcoin is based on POW, these individuals would be able to attack the
network as they are able to double spend their Bitcoins by creating
blocks faster than the rest of the network.

## Motivation

Cuckoo Cycle aims to minimize performance-per-dollar differences on
different hardware architectures and make mining on commodity hardware
more cost effective. This is to be achieved by making main memory
latency a bottleneck, since DRAM latencies have remained relatively
stable while cpu-speed and memory bandwidth vary highly across hardware
architecture and process technology. Our aim of a memory bound PoW
translates to the following desirable properties:

1. A target memory footprint that exceeds a single memory chip
2. A pattern of necessarily random memory accesses
3. Minimal computation per memory access
4. No feasible trade off of memory for time A memory bound PoW aims to
   take advantage of the huge economies of scale of commodity DRAM
   production to make DRAM chips the most cost-effective vehicle for
   mining. Just as SRAM is one order of magnitude faster but two orders
   more expensive than DRAM, so it is conceivable that development and
   production of custom memory chips for a memory bound PoW will incur a
   sufficient cost premium to wipe out any performance gains.

## Cuckoo Cycle

a memory bound graph-theoretic proof-of-work

Abstract: Cuckoo Cycle Whitepaper

>We introduce the first graph-theoretic proof-of-work system, based on
>finding small cycles or other structures in large random graphs. Such
>problems are trivially verifiable and arbitrarily scalable, presumably
>requiring memory linear in graph size to solve efficiently. Our cycle
>finding algorithm uses one bit per edge, and up to one bit per node.
>Runtime is linear in graph size and dominated by random access latency,
>ideal properties for a memory bound proof-of-work. We exhibit two
>alternative algorithms that allow for a memory-time trade-off
>(TMTO)---decreased memory usage, by a factor k, coupled with increased
>runtime, by a factor Ω(k). The constant implied in Ω() gives a notion of
>memory-hardness, which is shown to be dependent on cycle length, guiding
>the latter's choice. Our algorithms are shown to parallelize reasonably
>well.


***

| No | Type     | Source                                                          |
|:---|:---------|:----------------------------------------------------------------|
| 1  | doc      | [Cuckoo Cycle Whitepaper](https://eprint.iacr.org/2014/059.pdf) |
| 2  | code     | [Github Cuckoo Cycle](https://github.com/tromp/cuckoo)          |
| 3  | glossary | [cuckoo-cycle](Glossary#cuckoo-cycle)                           |
