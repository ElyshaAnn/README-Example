# Create a Token

This Solidity token contract allows for the creation and management of a simple cryptocurrency. It includes basic functionalities to mint (create) new tokens and burn (destroy) existing tokens. The contract maintains public variables for token details like name, abbreviation, and total supply. It also keeps a record of each address's token balance using a mapping. The mint function increases the total supply and updates balances, while the burn function decreases the total supply and balances, with checks to prevent burning more tokens than an address holds. This contract serves as a foundational framework for managing a digital token on the Ethereum blockchain.

## Description

This Solidity contract outlines the creation and management of a simple cryptocurrency token. The token contract includes functionalities for minting new tokens and burning existing ones, with the following main features:

Public Variables for Token Details:

Token Name: A string variable to store the name of the token.
Token Abbreviation (Token Abbrv.): A string variable to store a shorter version of the token's name.
Total Supply: A uint variable that keeps track of the total number of tokens in circulation.
Mapping of Addresses to Balances:

The contract uses a mapping to link each address (wallet) to its corresponding token balance. This mapping (address => uint) allows for efficient balance lookups and updates.
Mint Function:

Parameters: Takes an address and a value (number of tokens to be minted).
Functionality:
Increases the total supply of tokens by the specified value.
Increases the balance of the given address by the specified value.
This function allows new tokens to be created and assigned to a specific wallet.
Burn Function:

Parameters: Takes an address and a value (number of tokens to be burned).
Functionality:
Decreases the total supply of tokens by the specified value.
Decreases the balance of the given address by the specified value.
Condition: The function includes a check to ensure that the balance of the address is greater than or equal to the amount to be burned. This prevents burning more tokens than the address holds.
This function allows for the removal of tokens from circulation, effectively destroying them.

## Getting Started

### Executing program

* How to run the program
  
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file
  
* Step-by-step bullets
  
* Click Run or Compile button or Press CTRL + S to compile
* Go to Solidity Compiler and click Compile blue button
* Go to Deploy and run transact
* Click Deploy
* Then go to side bar, bottom left you will see right arrow then click it
* Then you can do all the transact like Mint, Burn.

  
* To mint Token, go to mint tab or the yellow button with named "Mint"
* Input value like 1-99999
* Copy the Account Address, you can see this top of the side bar named "Account"
* Paste to the Address
* Click transact to mint your Token

* To burn Token, go to burn tab or the yellow button same as Mint and named "Burn"
* Input value 1-99999
* Copy the Account Address, you can see this top of the side bar named "Account"
* Paste to the Address
* Click transact to burn your Token

* After that you can see the Token Abbreviation, Token name, and your Total Supply. That's All

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint256 public totalSupply;

    mapping(address => uint256) public balances;

    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance to burn");

        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
```

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

Elysha Ann Clarisse L. Agojo
422003322@ntc.edu.ph


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
