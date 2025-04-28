# Tachyon solvers - low latency ZK-Powered Solver Network for Open Intents Framework

## Thesis

The goal is to build a **solver network** for the **Open Intents Framework** that can **verify intent fulfillment** without relying on traditional **consensus mechanisms**.  

In the current system:
- Multiple solvers compete to fulfill a single intent.
- The first or most competitive solver wins and gets rewarded.
- Verification that the intent was fulfilled correctly is done through consensus — a group agrees the task was completed successfully.

**Problem:**  
- **Speed bottlenecks** due to consensus requirements.
- **Liquidity risks** if rewards are delayed.
- **Lower incentive** for solvers due to delayed compensation.

For more details

- Refer Across - https://docs.across.to/concepts/intents-architecture-in-across

- Refer OIF - https://www.openintents.xyz/

## Solution

Introduce **ZK (Zero-Knowledge) proofs** to create a **faster and more succinct** solver network.  
Instead of consensus, we will **cryptographically verify** key properties of fulfillment:

Three properties we need to prove:
1. The request was **fulfilled to the correct recipient**.
2. The request was **fulfilled at the lowest price**.
3. The request was **fulfilled by the correct solver on the given chain**.

By proving these properties, we can:
- Eliminate the need for consensus.
- Accelerate solver rewards.
- Improve liquidity and solver participation.

## Implementation

- Use **ZK proofs** to prove fulfillment conditions.
- Leverage **state proofs** (like Ethereum storage proofs and Merkle roots) to build verifiable claims.
- Use a platform like **ZK Verify** to verify proofs on-chain.
  - **ZK Verify** supports different proving schemes, including **NOIR** and those provided by **RISC Zero**.

Key components:
- **Proof generation:** Build ZK circuits to check fulfillment criteria.
- **Proof aggregation:** Aggregate different proofs if necessary.
- **Proof verification:** Post proofs to ZK Verify for on-chain verification.
- **Liquidity Management:** Ensure solvers have assets pre-funded to minimize delays.

**Summary:**  
A **ZK-powered solver network** ensures trustless, fast verification of intent fulfillment without relying on consensus or optimistic mechanisms, encouraging better liquidity and participation.

