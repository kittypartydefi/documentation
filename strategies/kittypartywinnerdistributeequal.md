# KittyPartyWinnerDistributeEqual

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/strategies/KittyPartyWinnerDistributeEqual.sol)

## Methods

### initiateCheckWinner()

#### function initiateCheckWinner(uint \_numberOfKittens)

Clear previous winners and push every Kitten index to winnerIndexes.

| Parameter Name    | Type | Description       |
| ----------------- | ---- | ----------------- |
| \_numberOfKittens | uint | number of Kittens |

## View Methods

### getWinners()

#### function getWinners()

Return array of winnerIndexes.

#### Return value

| Type       | Description             |
| ---------- | ----------------------- |
| uint256\[] | array of winnerIndexes. |

### getWinnerAtLocation()

#### function getWinnerAtLocation(uint i)

Returns winner at index i.

| Parameter Name | Type | Description     |
| -------------- | ---- | --------------- |
| i              | uint | index of winner |

#### Return values

| Type    | Description       |
| ------- | ----------------- |
| uint256 | winner at index i |

### getLength()

#### function getLength()

Returns length of winnerIndexes.

| Type | Description             |
| ---- | ----------------------- |
| uint | length of winnerIndexes |
