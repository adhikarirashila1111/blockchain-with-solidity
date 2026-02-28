# Collateralized Loan Smart Contract

A Solidity smart contract for managing ETH-collateralized loans on the Ethereum blockchain.

## ✅ Deployed Contract on Sepolia Testnet

**Contract Address:** `0xba3Bed98aB0A7B94a2f6401e04a6537e3F000e97`

**Etherscan Link:** https://sepolia.etherscan.io/address/0xba3Bed98aB0A7B94a2f6401e04a6537e3F000e97

## Project Structure

```
├── contracts/
│   └── CollateralizedLoan.sol   # Main smart contract
├── scripts/
│   └── deploy.js                # Deployment script
├── test/
│   └── CollateralizedLoan.js    # Test suite
├── .env                         # Environment variables (fill in your keys)
├── hardhat.config.js            # Hardhat configuration
└── package.json
```

## Setup

1. Install dependencies:
```bash
npm install
```

2. Fill in your `.env` file:
```
ACCOUNT_PRIVATE_KEY=your_wallet_private_key_here
INFURA_API_KEY=your_infura_api_key_here
ETHERSCAN_API_KEY=your_etherscan_api_key_here
```

## Commands

```bash
# Compile contracts
npx hardhat compile

# Run tests
npx hardhat test

# Deploy to Sepolia testnet
npx hardhat run scripts/deploy.js --network sepolia-testnet
```

## Contract Features

- **depositCollateralAndRequestLoan** – Borrower deposits ETH collateral and requests a loan
- **fundLoan** – Lender funds a loan request by sending the loan amount
- **repayLoan** – Borrower repays principal + interest to reclaim collateral
- **claimCollateral** – Lender claims collateral after borrower defaults (past due date)
- **calculateRepaymentAmount** – View function to calculate total repayment due

## Events

- `LoanRequested` – Emitted when a borrower requests a loan
- `LoanFunded` – Emitted when a lender funds a loan
- `LoanRepaid` – Emitted when a borrower repays a loan
- `CollateralClaimed` – Emitted when a lender claims collateral after default
