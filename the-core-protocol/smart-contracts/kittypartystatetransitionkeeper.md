---
description: >-
  This contract uses Chainlink Keepers to automate the function calls and timed
  transitions of the Kitty Party.
---

# KittyPartyStateTransitionKeeper

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyStateTransitionKeeper.sol)

## Methods

### addKPController()

#### function addKPController(address kpController)

Appends the address of the Kitty Party to an array containing the list of active Kitty Parties.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kpController   | address | address of Kitty Party |

### checkUpkeep()

#### function checkUpkeep(bytes calldata checkData)

Checks if the contract requires work to be done.

| Parameter Name | Type  | Description   |
| -------------- | ----- | ------------- |
| checkData      | bytes | Optional data |

#### Return value

| Parameter Name | Type  |                                                      |
| -------------- | ----- | ---------------------------------------------------- |
| upkeepNeeded   | bool  | true or false                                        |
| performData    | bytes | byte-encoded value of address and type of transition |

### performUpkeep()

#### function performUpkeep(bytes calldata performData)

Performs the work on the contract, if instructed by `checkUpkeep().`

| Parameter Name | Type  | Description                                          |
| -------------- | ----- | ---------------------------------------------------- |
| performData    | bytes | byte-encoded value of address and type of transition |
