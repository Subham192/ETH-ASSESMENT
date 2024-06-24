# ETH-ASSESMENT
CREATE A TOKEN.
# MY TOKEN
This Solidity program is a simple "MyToken" smart contract that demonstrates the basic functionality of creating, minting, and burning tokens on the Ethereum blockchain. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to understand how token contracts work.

#Description
# Description
This program is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract defines a token with a name, abbreviation, and total supply. It includes functions to mint new tokens and burn existing tokens. This program serves as a practical introduction to Solidity programming, and can be used as a foundation for more complex token projects in the future.

#Requirements
# Requirements
The contract has public variables to store details about the token (Token Name, Token Abbreviation, Total Supply).
The contract includes a mapping of addresses to balances (address => uint).
A mint function takes an address and a value, increasing the total supply and the balance of the specified address.
A burn function takes an address and a value, decreasing the total supply and the balance of the specified address, with conditions to ensure sufficient balance.

#Code
# Code
@@ -0,0 +1,21 @@
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount.
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint function. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // Public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if(balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}




#Getting Started
Executing Program
# Getting Started
# Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). 

@@ -0,0 +1,21 @@ Once the code is compiled, you can deploy the contract by clicking on the "Deplo

Once the contract is deployed, you can interact with it by calling the mint and burn functions. For example, to mint tokens, provide an address and a value to the mint function. Similarly, to burn tokens, provide an address and a value to the burn function. Ensure that the balance is sufficient when burning tokens.

# AUTHOR
@SUBHAM192

#License
# License
This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to customize this README file further according to your preferences or additional details about your project.

 
