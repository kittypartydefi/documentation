---
description: >-
  This contract represents individual Kitty Parties with methods for
  initializing, adding Kittens, depositing for yield, staking and choosing
  winners.
---

# KittyPartyController

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyController.sol)

## Methods

### initialize()

#### function initialize(KittyInitiator calldata \_kittyInitiator,KittyYieldArgs calldata \_kittyYieldArgs,KittyPartyFactoryArgs calldata \_kPFactory,address \_kreator,uint256 \_kreatorStake)

Initializes the Kitty Party contract with the arguments which include the Kitty Party options,yield,factory parameters, Kreator address and Kreator stake.

| Parameter Name   | Type     | Description                     |
| ---------------- | -------- | ------------------------------- |
| \_kittyInitiator | calldata | object of KittyInitiator        |
| \_kittyYieldArgs | calldata | object of KittyYieldArgs        |
| \_kPFactory      | calldata | object of KittyPartyFactoryArgs |
| \_kreator        | address  | address of Kreator              |
| \_kreatorStake   | uint256  | Kreator stake                   |

### setActivityInterval()

#### function setActivityInterval(uint8 \_timeToCollection)

Sets the time to collection for the Kitty Party.

| Parameter Name     | Type  | Description        |
| ------------------ | ----- | ------------------ |
| \_timeToCollection | uint8 | time to collection |

### setInviteHash()

#### function setInviteHash(bytes32 \_inviteHash)

Sets the invite hash of the Kitty Party.

| Parameter Name | Type    | Description                    |
| -------------- | ------- | ------------------------------ |
| \_inviteHash   | bytes32 | invite hash of the Kitty Party |

### changeState()

#### function changeState()

Allows the Kreator to make timed transitions for the Kitty Party stages.

#### Return values

| Parameter Name | Type | Description   |
| -------------- | ---- | ------------- |
| success        | bool | true or false |

### depositAndAddKittenToParty()

#### function depositAndAddKittenToParty(bytes32 \_inviteHash)

Performs the actual value transfer, adds Kitten to the party and deposits the value for yield generation.

| Parameter Name | Type     | Description                    |
| -------------- | -------- | ------------------------------ |
| \_inviteHash   | bytes32  | invite hash of the Kitty Party |

#### Return values

| Parameter Name | Type | Description   |
| -------------- | ---- | ------------- |
| success        | bool | true or false |



### setCallDataForYield()

#### function setCallDataForYield(bytes memory \_calldataForLock, bytes memory \_callDataForUnwind)

Sets the call data to lock and unwind yield.

| Parameter Name      | Type   | Description                   |
| ------------------- | ------ | ----------------------------- |
| \_calldataForLock   | bytes  | call data for locking yield   |
| \_callDataForUnwind | bytes  | call data for unwinding yield |

### addRoundDeposits()

#### function addRoundDeposits()

Adds deposits for each round.

#### Return value

| Type | Description   |
| ---- | ------------- |
| bool | true or false |

### depositForYield()

#### function depositForYield()

Checks whether there is sufficient balance and makes the transfer to the yield contract.

### applyInitialVerification()

#### function applyInitialVerification()

This is called by the Kreator once the Kreator verifies that all the Kittens have deposited initial amount for the first round.

### stopStaking()

#### function stopStaking()

Stop the staking and transfers the yield generated for the specific Kitty Party to the Treasury.

### payOrganizerFees()

#### function payOrganizerFees()

Calculates the fees for the DAO and the Kreator and mints the corresponding receipts.

### applyWinnerStrategy()

#### function applyWinnerStrategy()

This is where the receipts are given to the winners to redeem the actual amount from the Treasury contract.

### applyCompleteParty()

#### function applyCompleteParty()

This is to be called after party completion to mint the NFT's and tokens to the Kittens and Kreator.

### mintTokens()

#### function mintTokens(address mintTo,uint256 amount,uint256 tokenType)

Mint receipt tokens via the Kitty Party Accountant, receipt tokens can be claimed from the Treasury.

| Parameter Name | Type    | Description        |
| -------------- | ------- | ------------------ |
| mintTo         | address | address to mint to |
| amount         | uint256 | amount             |
| tokenType      | uint256 | type of token      |

### checkRefund()

#### function checkRefund()

Checks whether the minimum number of Kittens have joined the party in time and the Kreator can seek refund before the internal state changes to party started.
