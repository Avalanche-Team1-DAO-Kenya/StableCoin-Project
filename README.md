
# StableCoin Project

## Overview
The StableCoin Project is a decentralized stablecoin pegged to the USD, offering an algorithmic approach to maintaining stability. Users can mint the DSC token using Bitcoin or Ethereum as collateral, ensuring transparency and decentralization.

---

## Features
### Minting and Burning
- **Minting:** Users can mint DSC tokens by depositing sufficient collateral.  
- **Burning:** DSC tokens are burned when collateral is redeemed or liquidated.  

### Collateral Management
- **Supported Collateral:** Bitcoin and Ethereum.  
- **Health Factor:** Users must maintain a health factor above 1e18 to avoid liquidation.  
- **Liquidation Incentives:** Liquidators receive 10% of the liquidated user's collateral.  

### Core Functionalities
1. Deposit collateral.  
2. Redeem collateral.  
3. Mint DSC tokens.  
4. Calculate health factors.  
5. Liquidate undercollateralized users.  

---

## Getting Started

### Prerequisites
Ensure you have the following tools installed:  
- [Git](https://git-scm.com/downloads)  
- [Foundry](https://book.getfoundry.sh/)  


---

## Deployment
### Setting Up the Environment
1. Clone the repository and install dependencies:  
   ```bash  
   git clone <repository_url>  
   cd StableCoinProject  
   ```  

2. Configure your `.env` file with network details, private keys, and RPC URLs.  

### Deploy the Contracts
1. Deploy the `DecentralizedStableCoin.sol` contract:  
   ```bash  
   forge create --rpc-url <rpc_url> --private-key <private_key> src/DecentralizedStableCoin.sol  
   ```  
2. Deploy the `DSCEngine.sol` contract:  
   ```bash  
   forge create --rpc-url <rpc_url> --private-key <private_key> src/DSCEngine.sol  
   ```  

---

## Interacting with the Contracts
### Depositing Collateral
Users can deposit collateral to secure their DSC tokens by interacting with the `depositCollateral()` function:
```bash
cast send <DSCEngine_address> "depositCollateral(address collateralType, uint256 amount)" --rpc-url <rpc_url> --private-key <private_key>
```

### Minting DSC
Users can mint DSC tokens by interacting with the `mint()` function:  
```bash  
cast send <DSCEngine_address> "mint(uint256 amount)" --rpc-url <rpc_url> --private-key <private_key>  
```  

### Redeeming Collateral
Use the `redeem()` function to withdraw collateral:  
```bash  
cast send <DSCEngine_address> "redeem(uint256 amount)" --rpc-url <rpc_url> --private-key <private_key>  
```  

### Liquidating a User
Liquidators can call the `liquidate()` function:  
```bash  
cast send <DSCEngine_address> "liquidate(address user)" --rpc-url <rpc_url> --private-key <private_key>  
```  

---

## Project Structure
```
.
├── contracts
│   ├── DecentralizedStableCoin.sol # ERC20 token contract
│   ├── DSCEngine.sol               # Engine contract
├── test
│   ├── stablecoin.test.js          # Test cases
├── README.md                       # Project documentation
```  

---

## Tools and Resources
- [OpenZeppelin Contracts](https://openzeppelin.com/contracts/)  
- [Foundry Documentation](https://book.getfoundry.sh/)  

---

## Contributing
We welcome contributors to the StableCoin Project!  
1. Fork the repository.  
2. Create a new branch.  
3. Submit a pull request with your changes.  

---

## License
This project is licensed under the MIT License. See `LICENSE` for details.

