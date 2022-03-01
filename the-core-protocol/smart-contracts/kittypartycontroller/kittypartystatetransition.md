---
description: >-
  Contains information about the Kitty Party stages , the current stage and
  methods for timed transitions between stages.
---

# KittyPartyStateTransition

The source code can be found on [Github](https://github.com/kittypartydefi/1-kittyparty-contracts/blob/main/hardhat/contracts/KittyPartyStateTransition.sol)

## Methods

### getStage()

#### function getStage()

Returns the current stage of the Kitty Party.

#### Return value

| Type | Description                                                       |
| ---- | ----------------------------------------------------------------- |
| uint | Numerical value representing the current stage of the Kitty Party |

### timeSinceChange()

#### function timeSinceChange()

Number of epochs since the previous change in stage.

#### Return value

| Type | Description                                         |
| ---- | --------------------------------------------------- |
| uint | Number of epochs since the previous change in stage |

## View Methods

### isTransitionRequired()

#### function isTransitionRequired()

Checks whether stage transition is required for the Kitty Party and returns the current stage if transition is necessary else it returns the value of 88.

#### Return method

| Type  | Description                                                                  |
| ----- | ---------------------------------------------------------------------------- |
| uint8 | the current stage if transition is necessary else it returns the value of 88 |

###
