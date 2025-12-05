# 💠 MyToken (MTK) — ERC-20 Token Project

MyToken (MTK) is a fully functional ERC-20 token implemented in Solidity as part of a blockchain development learning project.  
This token demonstrates how Ethereum-based fungible assets operate, including balance management, transfers, approvals, and delegated spending.

---

## 🔹 Token Overview

| Property        | Value                                      |
|----------------|--------------------------------------------|
| **Name**       | MyToken                                    |
| **Symbol**     | MTK                                        |
| **Decimals**   | 18                                         |
| **Total Supply** | 1,000,000 MTK (1,000,000 × 10¹⁸ units)      |

**Constructor Input Used in Remix Deployment:**
```
1000000000000000000000000
```

---

## 🔹 Project Structure

```
my-token/
│
├── contracts/
│   └── MyToken.sol
│
├── screenshots/
│   ├── compilation.png
│   ├── deployment.png
│   ├── token-info.png
│   ├── transfer-test.png
│   ├── balances.png
│   ├── approval.png
│   └── transferFrom.png
│
└── README.md
```

---

## 🔹 Features Implemented (ERC-20 Standard)

- `balanceOf(address)` — returns token balance  
- `transfer(address,uint256)` — transfer tokens  
- `approve(address,uint256)` — authorize a spender  
- `allowance(address,address)` — check approved amount  
- `transferFrom(address,address,uint256)` — delegated transfer  
- Emits **Transfer** and **Approval** events  
- **Additional implementations:**
  - Validates against:
    - zero address transfers
    - insufficient balance
    - insufficient allowance
  - Uses Solidity 0.8.x (with automatic overflow protection)

---

## 🔹 How to Deploy (Remix IDE)

1. Open **https://remix.ethereum.org**
2. Create the file:  
   ```
   contracts/MyToken.sol
   ```
3. Paste the smart contract code
4. Compile using Solidity **0.8.x**
5. Deploy with:
   - **Environment:** Remix VM (Prague)
   - **Constructor argument:**  
     ```
     1000000000000000000000000
     ```

After deployment, the deployer automatically receives the entire total supply.

---

## 🔹 Usage Examples

### ✔ Check balance
```
balanceOf(0xYourAddress)
```

### ✔ Transfer 1 MTK
```
transfer(recipient, 1000000000000000000)
```

### ✔ Approve spender for 5 MTK
```
approve(spender, 5000000000000000000)
```

### ✔ Delegated transfer (spender performs transferFrom)
```
transferFrom(owner, recipient, 2000000000000000000)
```

---

## 🔹 Testing Performed (Screenshots Included)

The following functionality was tested in Remix and verified through event logs:

### ✔ Compilation  
Contract compiled successfully in Solidity 0.8.x.

### ✔ Deployment  
Deployed with correct total supply.

### ✔ Token Metadata  
- name() → MyToken  
- symbol() → MTK  
- decimals() → 18  
- totalSupply() → 1e24 units  

### ✔ Transfer Test  
- 1 MTK transferred from deployer to another account  
- Balances updated correctly  

### ✔ Approve Test  
- Deployer approved spender for 5 MTK  
- Approval event emitted  

### ✔ transferFrom Test  
- Spender successfully transferred 2 MTK on behalf of deployer  
- Allowance reduced correctly  
- Transfer event emitted  

All screenshots are located in `/screenshots`.

---

## 🔹 What I Learned

Through this project, I gained a solid understanding of:

- How ERC-20 tokens maintain balances using mappings  
- Why decimals matter (matching Ethereum’s 18-decimal standard)  
- How `transfer` differs from `transferFrom`  
- How allowances enable delegated transfers  
- Why event logs are critical for transparency and external indexing  
- How to use Remix IDE for compiling, deploying, and interacting with contracts  
- The importance of validating zero addresses and ensuring sufficient balances  
- How total supply is minted in the constructor  

This project provided practical skills in smart contract development and helped solidify core blockchain concepts.

---

## 🔹 License
This project is released under the **MIT License**.