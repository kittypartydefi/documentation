---
description: >-
  Contract which manages issuing of receipts, enables winners to claim their
  rewards and also issuing of refunds.
---

# KittyPartyAccountant

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyAccountant.sol)

## Methods

### \_\_KittyPartyAccountant\_init()

#### function \_\_KittyPartyAccountant\_init(address \_factoryContract)

Used for one time initialization, mints tokens to the factory contract.

| Parameter Name    | Type    | Description                               |
| ----------------- | ------- | ----------------------------------------- |
| \_factoryContract | address | address of the KittyPartyFactory Contract |

### mintToWinners

#### function mintToWinners(address kreator,address litterAddress,address kittyParty,uint256\[] memory winnerIndexes,uint256 amountToSent)

Mints the winner receipt tokens to the winners&#x20;

| Parameter Name | Type       | Description                     |
| -------------- | ---------- | ------------------------------- |
| kreator        | address    | address of the Kreator          |
| litterAddress  | address    | address of the Litter           |
| kittyParty     | address    | address of the party            |
| winnerIndexes  | uint256\[] | array of indexes of the winners |
| amountToSent   | uint256    | amount                          |

### \_checkApproved()

#### function \_checkApproved(address kreator, uint amountToSent)

Checks whether the Kreator has TOMCAT\_ROLE incase the amount is greater than 1000

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kreator        | address | address of the Kreator |
| amountToSent   | uint    | amount                 |

#### Return values

| Parameter Name     | Type | Description   |
| ------------------ | ---- | ------------- |
| approvalForKreator | bool | true or false |

### transferBadgesOnCompletion()

#### function transferBadgesOnCompletion(address litterAddress,address kittyParty)

Called by the Kitty party controller in order to safe transfer NFT badges to all the participants of a completed party.

| Parameter Name | Type    | Description                |
| -------------- | ------- | -------------------------- |
| litterAddress  | address | address of the Litter      |
| kittyParty     | address | address of the Kitty party |

### setupMinter()

#### function setupMinter(address kittyParty)&#x20;

Grants MINTER\_ROLE to the KittyParty. Gives approval to the child Contract to move factory tokens.

| Parameter Name | Type    | Description                |
| -------------- | ------- | -------------------------- |
| kittyParty     | address | address of the Kitty party |

### setTreasury()

#### function setTreasury(address \_treasuryContract)

Sets the treasury contract address.

| Parameter Name     | Type    | Description                                |
| ------------------ | ------- | ------------------------------------------ |
| \_treasuryContract | address | address of the KittyPartyTreasury Contract |

### setupTomcatList()

#### function setupTomcatList(address tomcat)

Adds a tomcat Kreator to the whitelist, via a DAO proposal

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| tomcat         | address | address of the tomcat |

