---
description: Factory contract for Kitty Parties.
---

# KittyPartyFactory

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyFactory.sol)

## Methods

### setKreatorFees()

#### setKreatorFees(uint8 \_kreatorFeesInBasisPoints)

Sets the Kreator fees in terms of basis points.

| Parameter Name             | Type  | Description                  |
| -------------------------- | ----- | ---------------------------- |
| \_kreatorFeesInBasisPoints | uint8 | Kreator fees in basis points |

### setDAOFees()

#### function setDAOFees(uint8 \_daoFeesInBasisPoints)

Sets DAO fees in terms of basis points.

| Parameter Name         | Type  | Description              |
| ---------------------- | ----- | ------------------------ |
| \_daoFeesInBasisPoints | uint8 | DAO fees in basis points |

### createKitty()

#### function createKitty(KittyInitiator calldata \_kittyInitiator,KittyYieldArgs calldata \_kittyYieldArgs)

Creates a Kitty Party with at most 20 Kittens.

| Parameter Name   | Type            | Description               |
| ---------------- | --------------- | ------------------------- |
| \_kittyInitiator | KittyInitiator  | object of KittyInitiator  |
| \_kittyYieldArgs | KittyYieldArgs  | object of KittyYieldArgs  |

#### Return values

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kittyAddress   | address | address of Kitty Party |

### setShouldReject()

#### function setShouldReject(bool \_value)

Sets the value of shouldReject.

| Parameter Name | Type | Description   |
| -------------- | ---- | ------------- |
| \_value        | bool | true or false |

## View Methods

### getMyKitties()

#### function getMyKitties(address candidateAddress)

Returns the list of Kitty Parties having candidateAddress as the Kreator.

| Parameter Name   | Type    | Description          |
| ---------------- | ------- | -------------------- |
| candidateAddress | address | address of candidate |

#### Return values

| Type       | Description      |
| ---------- | ---------------- |
| address\[] | array of address |
