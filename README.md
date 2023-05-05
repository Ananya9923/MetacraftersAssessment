# MyToken - A Simple Solidity Smart Contract

This is a basic Solidity smart contract that allows you to mint and burn tokens. It also includes a mapping of addresses to balances.

## Description

The Solidity code includes three public variables and two functions: mint and burn. The mint function increases the total supply of the token by the specified amount and adds that amount to the balance of the specified address. The burn function works in the opposite way: it decreases the total supply by the specified amount and subtracts that amount from the balance of the specified address.

### Executing program

To run the code, you can use the Remix editor IDE. Simply copy and paste the code into the editor, compile it, and deploy it.

```
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
    string public tokenname = "ANANYA"; 
    string public tokenAbbrv = "ANA"; 
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value; 
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public { 
        if (balances[_address] >= _value) {
            totalSupply -= _value; 
            balances[_address] -= _value;
        }
    }
}
```

## License

This project is licensed under the MIT License
