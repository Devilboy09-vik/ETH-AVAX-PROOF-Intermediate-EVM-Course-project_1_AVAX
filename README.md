# ETH-AVAX-PROOF-Intermediate-EVM-Course

## Project Title
This Solidity program is a simple contract that demonstrates the use of require(), assert(), and revert() statements in Solidity.The purpose of the contract is to demonstrate the error handling while creation and updation of driving license and vehicle ownership using require(), assert() and revert().
## Description
This is a simple project for simulating the development of smart contracts using Remix IDE and the Solidity language .Firstly We use the modifier and constructor. Then make deposit,withdraw,getbalance and totalbalance function.In this project we use the error handling concept. so, We use the revert() , require() and assert() .

### Getting started
## Installing
* To run the project code, you need an IDE where you can run the Solidity language.One such IDE is the online Remix IDE (https://remix.ethereum.org/), which you can run on any browser of your choice.
* The code in this project can be used by simply copying it to the editor of any IDE where you can run Solidity version 0.8.7.
## Executing program
* How to run the program

1. Copy the Solidity code provided in the "project_1_AVAX" file.

2. Open Remix IDE (https://remix.ethereum.org/).

3. In the Remix IDE, create a new file and paste the copied code into it.

4. Compile the Code by either pressing "Ctrl + S" to compile the code or using the Compile button in the Remix IDE interface.

5. Use the Deploy button in the Remix IDE to deploy the contract to a local Ethereum network or a test network.

6. Use the deployed contract's interface in Remix IDE  and then deposit the ether and then input some ether in the deposit button and then call the deposit function and then call the getbalance and total balance.

## Code
```
solidity // SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

contract DrivingLicense { // Mapping to store the age of each user mapping(address => uint) public age;

// Mapping to store whether a user owns a vehicle
mapping(address => bool) public ownsVehicle;

// Function to set the age of a user
function setAge(uint _age) public {
    // Using require to ensure the age is a reasonable value
    require(_age > 0 && _age < 150, "Invalid age provided.");

    // Setting the age for the sender's address
    age[msg.sender] = _age;
}

// Function to set vehicle ownership status of a user
function setVehicleOwnership(bool _ownsVehicle) public {
    // Setting the vehicle ownership status for the sender's address
    ownsVehicle[msg.sender] = _ownsVehicle;
}

// Function to check eligibility for a driving license
function checkEligibility() public view returns (bool) {
    uint userAge = age[msg.sender];
    bool vehicleOwnership = ownsVehicle[msg.sender];

    // Using require to ensure the age is set
    require(userAge > 0, "Age is not set. Please set your age first.");

    // Check if the user is eligible for a driving license
    if (userAge < 18) {
        // Using revert to indicate the user is not eligible
        revert("You are not eligible for a driving license.");
    }

    // Using assert to ensure the user's age is indeed 18 or greater
    assert(vehicleOwnership == true);

    // Returning the eligibility status in boolean form
    return true;
}
}
```

## Help 

If you encounter any issues or have any questions, here are some common solutions:

1. Ensure you are using Solidity version 0.8.7 or later.

2. Check the Remix IDE console for error messages and follow the guidance provided.
## Authors
Contributors names and contact info

Vikram Garg gmail: vikramgarg979@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
