# challenge21_Repo
A project to develop a monetary system for the new Mars colony. 

## User Story
Role: Martian Aerospace Agency Fintech Project Lead

Goal: To develop a monetary system for the new Mars colony based on blockchain technology, and to define a new cryptocurrency called KaseiCoin. (“Kasei” means “Mars” in Japanese.)

Reason: KaseiCoin will be a fungible token that is ERC-20 compliant. also launch a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin

## Requirements
1. Create a smart contract that defines KaseiCoin as an ERC-20 token

2. Define the KaseiCoin crowdsale contract

3. Create the KaseiCoin Deployer Contract

4. Deploy the crowdsale to a local blockchain using Remix, MetaMask, and Ganache.

5. Optional: Eextend the crowdsale contract to enhance its functionality by Using OpenZeppelin

## Libraries and dependencies
The following libraries and dependencies were deployed:
- Remix IDE
- Ganache
- MetaMask


## Evaluation Evidence 
Screenshots from each subsection of the project work:

### Create the KaseiCoin Token Contract
Create, compile and deploy Smart contract that defines KaseiCoin as an ERC-20 token.

1. Import the provided `KaseiCoin.sol` starter file into the Remix IDE.

2. Import the following contracts from the OpenZeppelin library:

    * `ERC20`, `ERC20Detailed`, `ERC20Mintable`

3. Define a contract for the KaseiCoin token called `KaseiCoin`, and have the contract inherit the three contracts that you just imported from OpenZeppelin.

4. Inside of your `KaseiCoin` contract, add a constructor with the following parameters: `name`, `symbol`, and `initial_supply`.

5. Then, as part of your constructor definition, add a call to the `ERC20Detailed` contract’s constructor, passing the parameters `name`, `symbol`, and `18`. Recall that 18 is the value for the `decimal` parameter.

6. Compile the contract using compiler version 0.5.0.

7. Check for any errors and debug as needed.

8. Display KaseiCoin Deployer screenshot
![Deploy KaseiCoin](https://user-images.githubusercontent.com/88909565/154812203-039c69e3-7146-417f-8877-0a76bf90a7ef.png)

9. Display KaseiCoin Compiler screenshot 
![KaseiCoin sol Compiler screenshot](https://user-images.githubusercontent.com/88909565/154812217-36c17746-1d50-48e8-8da3-e182b6632b51.png)

### Create the KaseiCoin Crowdsale Contract
Define the KaseiCoin crowdsale contract to inherit Crowsale and Minted Crowdale from OpenZeppelin contracts
1. Import the provided `KaseiCoinCrowdsale.sol` starter code into the Remix IDE.

2. Have this contract inherit the following OpenZeppelin contracts:

* `Crowdsale`

* `MintedCrowdsale`

3. Within the `KaisenCoinCrowdsale` constructor, provide parameters for all of the features of your crowdsale, such as `rate`, `wallet` (where the funds that the token raises should be deposited), and `token`. Configure these parameters as you see fit for your KaseiCoin token.

4. Compile the contract using compiler version 0.5.0.

5. Check for any errors and debug as needed.

6. Display screenshot of the successful compilation of the KaseiCrowdsale contract
![KaseiCoinCrowdsale sol Compiler screenshot](https://user-images.githubusercontent.com/88909565/154812269-30c43139-b94e-4e6b-913e-bf3fef8b2a55.png)

### Create the KaseiCoin Deployer Contract

1. Create an `address public` variable called `kasei_token_address`, which will store `KaseiCoin`’s address once that contract has been deployed.

2. Create an `address public` variable called `kasei_crowdsale_address`, which will store `KaseiCoinCrowdsale`'s address once that contract has been deployed.

3. Add the following parameters to the constructor for the `KaseiCoinCrowdsaleDeployer` contract: `name`, `symbol`, and `wallet`.

4. Inside of the constructor body (between the curly braces), complete the following steps:

    * Create a new instance of the `KaseiCoinToken` contract.

    * Assign the KaseiCoin token contract’s address to the `kasei_token_address` variable. This will allow you to easily fetch the token's address later.

    * Create a new instance of the `KaseiCoinCrowdsale` contract using the following parameters:

       * `rate` (Set `rate` equal to 1 in order to maintain parity with ether.)

       * `wallet` (Pass `wallet` in from the main constructor. This is the wallet that will get paid all of the ether raised by the crowdsale contract.)

       * `token` (This should be the `token` variable where `KaseiCoin` is stored.)

    * Assign the KaseiCoin crowdsale contract’s address to the `kasei_crowdsale_address` variable. This will allow you to easily fetch the crowdsale’s address later.

    * Set the `KaseiCoinCrowdsale` contract as a minter.

    * Have the `KaseiCoinCrowdsaleDeployer` renounce its minter role.

5. Compile the contract using compiler version 0.5.0.

6. Check for any errors and debug as needed.

7. Display Screenshot of the successful compilation of the KaseiCoin Deployer Contract
![Deploy KaseiCoin](https://user-images.githubusercontent.com/88909565/154812302-64416536-9382-411a-a4f7-94272d80673d.png)

### Deploy the Crowdsale to a Local Blockchain
1. Deploy the crowdsale to a local blockchain with Remix, MetaMask, and Ganache.

2. Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances associated with those accounts.

3. After purchasing tokens with one or more test accounts, view the total supply of minted tokens and the amount of wei that has been raised in the crowdsale contract.

4. Display Screeshot of the deployment of CrowdSale usining Remix, Metamask and Ganache  

![Deploy CrowdSale_Remix_Metamask_Ganache](https://user-images.githubusercontent.com/88909565/154812249-8fc910fe-b85d-4d6e-96e2-ee9d9e92c7ee.png)

#### Optional: Extend the Crowdsale Contract by Using OpenZeppelin
This sections was started but commented out and will be further reviewed and executed as part of persona interest to implement these optional steps.

