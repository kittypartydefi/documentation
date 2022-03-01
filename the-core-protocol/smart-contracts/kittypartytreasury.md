---
description: >-
  Manages funds corresponding to the Kitty Parties and contains methods which
  allows winners to redeem their receipt tokens and for the DAO to withdraw the
  funds.
---

# KittyPartyTreasury

&#x20;The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyTreasury.sol)

## Methods

### \_\_KittyPartyTreasury\_init()

#### function \_\_KittyPartyTreasury\_init(address \_dai\_address,address \_kpt\_address,address \_daoAddress,address \_accountantContract)

Initialization for the Treasury contract.

| Parameter Name       | Type    | Description                                    |
| -------------------- | ------- | ---------------------------------------------- |
| \_dai                | address | address of DAI Token                           |
| \_kpt                | address | address of KPT Token                           |
| \_daoAddress         | address | address of the DAO safe                        |
| \_accountantContract | address | address of the Kitty Party Accountant Contract |

### setBonusKPT()

#### function setBonusKPT(uint \_amountToReward)

Sets the amount to be rewarded in KPT.

| Parameter Name   | Type | Description          |
| ---------------- | ---- | -------------------- |
| \_amountToReward | uint | reward amount in KPT |

### setDAOAddress()

#### function setDAOAddress(address \_daoAddress)

Sets the DAO address.

| Parameter Name | Type    | Description    |
| -------------- | ------- | -------------- |
| \_daoAddress   | address | address of DAO |

### redeemTokens()

#### function redeemTokens(uint256 redeemAmount)

Allows winners to redeem receipt tokens and receive DAI in return.

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| redeemAmount   | uint256 | amount to be redeemed |

### withdraw()

#### function withdraw(IERC20 token, address recipient, uint256 amount)

Allows the DAO to withdraw the funds in the Treasury contract.

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| token          | IERC20  | token to be withdrawn |
| recipient      | address | address of recipient  |
| amount         | uint256 | amount to withdraw    |
