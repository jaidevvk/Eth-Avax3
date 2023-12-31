# Eth-Avax3

In the project, I deployed the contract to hardhat network and on remix to show the working of each function

## Description

In this module , I have created the contract which was generated by openzeppelin by entering certain details like token name- Electricity and Token Symbol- ETC and checking the Mintable,Ownable, Burnable boxes. The openzeppelin libraries get imported and several functions get added.

## Getting Started

### Deploying the contract on Remix

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., thirdmodule.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts@5.0.0/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts@5.0.0/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts@5.0.0/access/Ownable.sol";

contract Electricity is ERC20, ERC20Burnable, Ownable {
    constructor(address initialOwner)
        ERC20("Electricity", "ETC")
        Ownable(initialOwner)
    {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile thirdmodule.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "thirdmodule" contract from the dropdown menu, and then click on the "Deploy" button.

But make sure, you enter the owner's address into the box next to deploy so that owner's address gets initialised. 
### Deploying the contract on Hardhat Network

To deploy it to hardhat network, run the command:

```
npx hardhat run scripts/deploy.js
```
The contract gets deployed to hardhat network and the address is shown in the terminal

## Authors

Jaidev K[@jaidevvk12@gmail.com]

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
