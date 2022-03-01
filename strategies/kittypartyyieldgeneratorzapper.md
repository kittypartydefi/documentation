# KittyPartyYieldGeneratorZapper

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/strategies/KittyPartyYieldGeneratorZapper.sol).

## Methods

### \_\_KittyPartyYieldGeneratorZapper\_init()

#### function \_\_KittyPartyYieldGeneratorZapper\_init(address treasuryContractParam)

<>

| Parameter Name        | Type    | Description                  |
| --------------------- | ------- | ---------------------------- |
| treasuryContractParam | address | address of Treasury contract |

### setAllowanceZapIn()

#### function setAllowanceZapIn()

<>

### setAllowanceZapOut()

#### function setAllowanceZapOut()

<>

### createLockedValue()

#### function createLockedValue(bytes calldata zapCallData)

Deposits DAI and receives equivalent amount of tokens.

| Parameter Name | Type  | Description |
| -------------- | ----- | ----------- |
| zapCallData    | bytes |             |

#### Return value

| Parameter Name | Type    |                  |
| -------------- | ------- | ---------------- |
| vaultTokensRec | uint256 | number of tokens |

### unwindLockedValue()

#### function unwindLockedValue(bytes calldata zapCallData)

Unlocks value and sends it to the treasury contract

| Parameter Name | Type  | Description |
| -------------- | ----- | ----------- |
| zapCallData    | bytes |             |

#### Return value

| Parameter Name | Type    |                                |
| -------------- | ------- | ------------------------------ |
| tokensRec      | uint256 |  yield generated in last round |

### setPlatformDepositContractAddress()

#### function setPlatformDepositContractAddress(address payable \_zapInContract)

Sets the address of Zappin Contract.

| Parameter Name  | Type    | Description                 |
| --------------- | ------- | --------------------------- |
| \_zapInContract | address | address of Zappin Contract  |

### setPlatformRewardContractAddress()

### setPartyInfo()

#### function setPartyInfo(address \_sellTokenAddress, address \_lpTokenAddress)

Allows Party to set their own pair of addresses for yield

| Parameter Name     | Type    | Description           |
| ------------------ | ------- | --------------------- |
| \_sellTokenAddress | address | address of sell token |
| \_lpTokenAddress   | address | address of Ip token   |

## View Methods

### treasuryAddress()

#### function treasuryAddress()

Returns treasury contract address.

#### Return value

| Parameter Name          | Type    |                              |
| ----------------------- | ------- | ---------------------------- |
| treasuryContractAddress | address | address of Treasury contract |

### lockedAmount()

#### function lockedAmount(address kittyParty)

Returns locked amount of a Kitty Party.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kittyParty     | address | address of Kitty Party |

#### Return value

| Parameter Name   | Type    |                |
| ---------------- | ------- | -------------- |
| totalLockedValue | uint256 | locked amount  |

### yieldGenerated()

#### function yieldGenerated(address kittyParty)

Returns the yield generated in the last round.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kittyParty     | address | address of Kitty Party |

#### Return value

| Type    |                                   |
| ------- | --------------------------------- |
| uint256 | yield generated in the last round |

### lockedPool()

#### function lockedPool(address kittyParty)

Returns the pool address.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kittyParty     | address | address of Kitty Party |

#### Return value

| Type    |                     |
| ------- | ------------------- |
| address | address of the pool |
