# Solidity-final-project: Create a Token
 
This solidity program allows us to create our own very simple smart contract with some functionality. We can also see the basic syntax and functionality of the Solidity programming language in this program.

## Description
This create a token program is a simple program written in Solidity which is a programming language used for developing smart contracts on the Ethereum blockchain. The contract has public variables that store data about the token. It also has a mapping variable that maps unique addresses to the balance of the token. It also has two functions which are mintToken and burnToken, which creates new tokens and deletes existing tokens, respectively.

## Getting Started

### Executing the program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., FinalAssessment.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "Chowchow";
    string public tokenAbbreviation = "CHW";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mintToken(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burnToken(address _address, uint _value) public {  
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;   
        }
    }
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile FinalAssessment.sol" button.

After compilation, the contract can be deployed by clicking the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "FinalAssessment" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, click on the "FinalAssessment" contract first on the left-hand sidebar, you can interact with it by clicking the mintToken function which asks an input for the amount of token you want to create for a specific address. You can also click the burnToken function which asks an input for the amount of token you want to burn for a specific address. You can click on the variables as well to see the value they store, in this case the details about the Token. The totalSupply variable will change depending on the input amount you enter on the functions. 

## Authors

Kenneth Lim
Email : 202010039@fit.edu.ph



## License

This project is licensed under the MIT License - see the LICENSE.md file for details