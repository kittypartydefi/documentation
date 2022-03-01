# KittyPartyYieldGeneratorAave

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/strategies/KittyPartyYieldGeneratorAave.sol)

## Methods

### \_\_KittyPartyYieldGeneratorAave\_init()

#### function \_\_KittyPartyYieldGeneratorAave\_init(address treasuryContractParam)

<>

| Parameter Name        | Type    | Description                  |
| --------------------- | ------- | ---------------------------- |
| treasuryContractParam | address | address of Treasury contract |

### setAllowanceDeposit()

#### function setAllowanceDeposit(address \_kittyParty)

<>

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| \_kittyParty   | address | address of Kitty Party |

### setAllowanceWithdraw()

#### function setAllowanceWithdraw(address \_kittyParty)

Checks if the contract requires work to be done.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| \_kittyParty   | address | address of Kitty Party |

### createLockedValue()

#### function createLockedValue(bytes calldata)

Deposits DAI and receives equivalent amount of tokens.

| Parameter Name | Type  | Description |
| -------------- | ----- | ----------- |
| calldata       | bytes |             |

#### Return value

| Parameter Name | Type    |                  |
| -------------- | ------- | ---------------- |
| vaultTokensRec | uint256 | number of tokens |

### unwindLockedValue()

#### function unwindLockedValue(bytes calldata)

Claims accrued rewards and withdraws the deposited tokens and sends them to the treasury contract.

| Parameter Name | Type  | Description |
| -------------- | ----- | ----------- |
| calldata       | bytes |             |

#### Return value

| Parameter Name | Type    |                                |
| -------------- | ------- | ------------------------------ |
| tokensRec      | uint256 |  yield generated in last round |

### setPlatformDepositContractAddress()

#### function setPlatformDepositContractAddress(address payable \_AaveContract)

Sets the address of Aave Contract.

| Parameter Name | Type    | Description               |
| -------------- | ------- | ------------------------- |
| \_AaveContract | address | address of Aave Contract  |

### setPlatformRewardContractAddress()

#### function setPlatformRewardContractAddress(address payable \_AaveRewardContract, address \_rewardTokenAddress)

Sets the Aave reward contract and the address of reward token.

| Parameter Name       | Type    | Description                     |
| -------------------- | ------- | ------------------------------- |
| \_AaveRewardContract | address | address of Aave reward contract |
| \_rewardTokenAddress | address | address of reward token         |

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

### yieldCurrent()

#### function yieldCurrent(address kittyParty)

Returns the yield to be generated in the current round.

| Parameter Name | Type    | Description            |
| -------------- | ------- | ---------------------- |
| kittyParty     | address | address of Kitty Party |

#### Return value

| Parameter Name                   | Type    |                                            |
| -------------------------------- | ------- | ------------------------------------------ |
| yieldToBeGeneratedInCurrentRound | uint256 | yield to be generated in the current round |

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
