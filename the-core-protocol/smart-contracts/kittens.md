---
description: >-
  The Kittens contract is used to describe the types of Kitty Party and their
  respective options.
---

# Kittens

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/Kittens.sol)

## Methods

### addKitten()

#### function addKitten(address value)&#x20;

Adds a kitten to the particular party. It checks whether the kitten does not previously  exist in the contract else it reverts.

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| value          | address | address of the Kitten |

### setupKittyParty()

#### function setupKittyParty(address childContract)

Used to grant the KITTYPARTY to the child contract.

## View Methods

### getList()

#### function getList(address kittyParty)

Returns the list of kittens in the specified party.

| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| kittyParty     | address | address of the party |

#### Return values

| Type      | Description      |
| --------- | ---------------- |
| Kitten\[] | array of Kittens |

### getLength()

#### function getLength(address kittyParty)

Returns the number of kittens in the party.

| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| kittyParty     | address | address of the party |

#### Return values

| Type    | Description       |
| ------- | ----------------- |
| uint256 | number of Kittens |

### getValueAt()

#### function getValueAt(address kittyParty, uint256 i)

Returns the kitten corresponding to the index within the array.

| Parameter Name | Type    | Description          |
| -------------- | ------- | -------------------- |
| kittyParty     | address | address of the party |
| i              | uint256 | index                |

#### Return values

| Type   | Description                         |
| ------ | ----------------------------------- |
| Kitten | Kitten corresponding to the index i |

### getIndex()

#### function getIndex(address kittyParty, address \_kitten)

Returns the index in the Kitten array corresponding to the address of the kitten.

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| kittyParty     | address | address of the party  |
| \_kitten       | address | address of the Kitten |

#### Return values

| Type    | Description |
| ------- | ----------- |
| uint256 | index       |

### checkExists()

#### function checkExists(address kittyParty, address \_kitten)

Checks if a specific kitten exists in a party

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| kittyParty     | address | address of the party  |
| \_kitten       | address | address of the Kitten |

#### Return values

| Type | Description   |
| ---- | ------------- |
| bool | true or false |

### getAllList()

#### function getAllList()

Returns the entire list of kittens in the master litter

#### Return values

| Type      | Description      |
| --------- | ---------------- |
| Kitten\[] | array of Kittens |

### getAllLength()

#### function getAllLength()

Returns the total number of kittens in the master Litter

#### Return values

| Type    | Description       |
| ------- | ----------------- |
| uint256 | number of Kittens |

### getAllValueAt

#### function getAllValueAt(uint256 i)

Returns the Kitten corresponding to the index in the Kitten list within the master Litter.

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| i              | uint256  | index       |

#### Return values

| Type   | Description |
| ------ | ----------- |
| Kitten | Kitten      |

### getIndex

#### function getIndex(address \_kitten)

Returns the index of the Kitten within the master Litter.

| Parameter Name | Type    | Description           |
| -------------- | ------- | --------------------- |
| \_kitten       | address | address of the Kitten |

#### Return values

| Type    | Description |
| ------- | ----------- |
| uint256 | index       |

### checkAllExists

#### function checkAllExists(address \_kitten)

Checks if the Kitten is present in the master Litter.

| Parameter Name | Type    | Description       |
| -------------- | ------- | ----------------- |
| \_kitten       | address | address of Kitten |

#### Return values

| Type | Description   |
| ---- | ------------- |
| bool | true or false |

