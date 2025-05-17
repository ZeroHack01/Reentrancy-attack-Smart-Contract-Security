# Smart Contract Security - Reentrancy Attack 🛡️

![Smart Contract Security Banner](https://via.placeholder.com/800x200/4B0082/FFFFFF?text=Smart+Contract+Security)

## 🚨 Overview
A comprehensive, practical demonstration of the **reentrancy vulnerability** - one of the most notorious security flaws in smart contract development - and essential protection strategies to safeguard your contracts.

## 🔧 Technology Stack & Dependencies

| Technology | Purpose |
|------------|---------|
| **Solidity** | Writing secure Smart Contracts |
| **JavaScript** | Handling contract interactions |
| **[NodeJS](https://nodejs.org/en/)** | Creating Hardhat projects and managing dependencies |
| **[Ethers.js](https://docs.ethers.io/v5/)** | Interacting with blockchain contracts via JavaScript |

## 🚀 Getting Started

### 1. Clone/Download the Repository
```bash
git clone https://github.com/Cicada-3301Bank/Reentrancy-attack-Smart-Contract-Security.git
cd Reentrancy-attack-Smart-Contract-Security
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Compile Smart Contracts
```bash
npx hardhat compile
```

### 4. Test and Perform Attack Simulation
```bash
npx hardhat test
```

## 📚 What You'll Learn

- Understanding the mechanics of reentrancy attacks
- Identifying vulnerable contract patterns
- Implementing protection measures:
  - Checks-Effects-Interactions pattern
  - ReentrancyGuard implementation
  - State management best practices

## 🔐 Security Best Practices

- ✅ Always update state variables before external calls
- ✅ Implement reentrancy guards for critical functions
- ✅ Use pull payment patterns instead of push where possible
- ✅ Apply the principle of least privilege

## 📊 Example Attack Flow

```mermaid
sequenceDiagram
    participant Attacker
    participant Malicious Contract
    participant Vulnerable Contract
    
    Attacker->>Malicious Contract: Deploy
    Attacker->>Malicious Contract: Attack(VulnerableContract)
    Malicious Contract->>Vulnerable Contract: deposit()
    Malicious Contract->>Vulnerable Contract: withdraw()
    Vulnerable Contract->>Malicious Contract: send ETH (fallback function)
    Malicious Contract->>Vulnerable Contract: withdraw() [REENTRY]
    Note over Vulnerable Contract: State not yet updated!
    Vulnerable Contract->>Malicious Contract: send ETH again
    Note over Vulnerable Contract, Malicious Contract: Loop continues...
    Malicious Contract->>Attacker: Stolen funds
```

## 💡 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<div align="center">
  <h3>⚠️ Educational Purposes Only ⚠️</h3>
  <p>This repository is intended for educational purposes to help developers understand and prevent security vulnerabilities.</p>
</div>
