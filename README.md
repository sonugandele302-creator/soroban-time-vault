# soroban-time-vault
A simple time-locked smart contract on Soroban (Stellar)

# Soroban Time-Vault

A **time-locked smart contract** built on **Soroban**, Stellar’s smart contract platform written in **Rust**.  
This contract allows users to **lock assets** until a specific **unlock time**, after which they can withdraw safely.  

---

##  Project Overview
**Soroban Time-Vault** is designed to demonstrate how smart contracts can manage timed access to funds on the Stellar blockchain.

It works like a **digital fixed deposit** — once assets are locked, they remain inaccessible until the preset unlock time is reached.

---

##  Features
-  **Time-locking**: Deposit tokens that can’t be withdrawn until the specified timestamp.  
-  **Automated execution**: Smart contract enforces conditions without manual intervention.  
-  **Transparency**: All transactions and states are visible on the blockchain.  
-  **Learning-friendly**: A great starter project for learning Soroban and Rust smart contracts.

---

 Contract Logic
The contract mainly performs three operations:

1. **Deposit Funds**
   - Users specify an `unlock_time` (future timestamp).
   - Assets are locked in the contract.

2. **Withdraw Funds**
   - Allowed only if the current blockchain time ≥ `unlock_time`.

3. **Check Balance**
   - Users can view their deposited balance and unlock status.

**Pseudo Logic:**
```rust
if current_time >= unlock_time {
    allow_withdraw();
} else {
    reject_transaction();
}
