# Guardians for the KittyParty Verse

This is the home of the guardians, a set of erc721 smart contracts that will be minted on mainnet, post that each owner of the specific NFT will be allowed to initiate a message to polygon such that a batch of 100 Apprentice tokens can then be minted on that chain.

This has been build on top of the fxportal bridge built by polygon details under FxPortal below.

Parent <> L1 and child <> L2 mean the same. The concept being that apprentices can travel to different L2 networks over time to develop that network. There is no centralized registry of which chain a particular NFT is on, and this can in future be developed as an extension if required.

### Minting Process

We are following a cross chain mint pattern. Since our story revolves around the guardians who guard the Ethereum Kitty Party Metaverse and are calling forth apprentices from polygon.

![DiagramsequenceDiagram](https://raw.githubusercontent.com/kittypartydefi/1-kittyparty-guardians/main/assets/guardianNFT.png)



<mark style="color:blue;">Sequence Diagram</mark>&#x20;

<mark style="color:blue;">Guardian->> KPRootGuardianNFT: awakenGuardian(\_tokenURI);</mark>&#x20;

<mark style="color:blue;">Guardian->> KPRootFxTunnel: bringForthTheApprentices(guardianId, message)</mark>&#x20;

<mark style="color:blue;">KPRootFxTunnel->> KPChildFxTunnel: bringForthTheApprentices(guardianId, message)</mark>&#x20;

<mark style="color:blue;">Note right of KPRootFxTunnel: State Transfer based message transfer handled by polygon</mark>&#x20;

<mark style="color:blue;">KPChildFxTunnel->> KPChildGuardianNFT: guardian.awakenTribe(guardianId);</mark>&#x20;

<mark style="color:blue;">Apprentice ->> KPChildGuardianNFT: joinTheForce(guardianId)</mark>&#x20;

<mark style="color:blue;">Note right of KPChildGuardianNFT: Here can mint 88 tokens per guardian token</mark>

This is the cross chain flow for the guardian contracts, in the first part, we are sending a message via state channel transfer to allow the mint process in the child chain for that particular tribe.

Once that process is completed and there are 88 guardians in the parent chain and 8888 tokens in the child chain. Then we move to the next phase which is allowing them to do cross chain transfer.

### Cross chain message details

The message that gets passed is the token id of the guardian and the attribute set. The attribute set denotes the zodiac and the power of the guardian. This cannot be computed from token id because we utilize the Chainlink VRF to randomize to increase fairness.

### Cross Chain Future Transport

We have to enable a DAO controlled mint adapter, meaning that the DAO can set an array of addresses that can call the mint function. This is required

#### Design Proposal

We create a state based transition and set flag, only when this flag is true, does cross chain movement work. Phase 1 -> Initial Mint and Waking up the forces Phase 2 -> After an era of 1 year the NFT's will be cross chain compatible

`graph LR`&#x20;

`A((Initial Awakening of Guardians)) -- T + 365days --> B((CROSSCHAIN))`

**Implementation**

The implementation can be that when the phase 2 has started, the following happens

1. The DAO can allow certain adapter contracts to mint Guardians on any chain as long as they are not in the deposit adapter.
2. The total supply does not go above 8888 on any chain.
3. Burn will still not be allowed

At this stage we will create an additional mint function which can only be called by the DAO and a burn function which again can only be called by the adapter.

So a whitelist of a single address which can be added to by the DAO that can mint and burn in future for each chain there will only 1 adapter.

We have instantiated the token\_supply on the child chain to start at 88.

**Possible Issues**

1. Users create their own mapping and mint in different L2 chain - This is fine because this wont be recognized by our DAO.

## Existing Polygon documentation below

### fx-portal(Flexible portal)

FxPortal for Polygon(prev Matic)Chain. No mapping. Seamless communication with Ethereum Network.

Audit - [Fx-Portal Contracts Audit by Halborn](https://github.com/fx-portal/contracts/blob/main/Polygon\_FX\_Portal\_Smart\_Contract\_Security\_Audit\_Halborn\_v1\_0%20\(1\).pdf)

#### What is Fx bridge (fx-portal)?

**It is a powerful yet simple implementation Polygon** [**state sync**](https://docs.matic.network/docs/contribute/state-sync) **mechanism. Polygon PoS bridge is based on it. The code in the `examples` folder are examples of the usage of this methodology. You can use these examples to build your own implementations or own custom bridge.**

In short, it's Meta bridge. This bridge allows any state-syncs without mapping.

**Some use-cases of Fx-portal**

* [ERC20 token tranfer from Ethereum to Matic-Chain without mapping request](https://github.com/jdkanani/fx-portal/tree/main/contracts/examples/erc20-transfer)
* [Lazy minting of ERC20 tokens on MaticChain](https://github.com/jdkanani/fx-portal/tree/main/contracts/examples/mintable-erc20-transfer)
* [State Transfer between Ethereum-Matic](https://github.com/jdkanani/fx-portal/tree/main/contracts/examples/state-transfer)

**What about** [**PoS portal**](https://docs.matic.network/docs/develop/ethereum-matic/pos/getting-started)**?**

PoS Portal is another bridge, but it works only for few ERC standards and requires mappings. It is more developer-friendly, allows customization without much headache.

While Fx-portal focuses on permissionless-ness and flexibility, a developer might have to write more code but more customizable than PoS Portal. It requires no mapping.

**Can I build my bridge?**

Yes. You can check docs here: [https://docs.matic.network/docs/develop/l1-l2-communication/ethereum-to-matic](https://docs.matic.network/docs/develop/l1-l2-communication/ethereum-to-matic) [https://docs.matic.network/docs/develop/l1-l2-communication/matic-to-ethereum](https://docs.matic.network/docs/develop/l1-l2-communication/matic-to-ethereum)

#### What are FxChild and FxRoot?

`FxChild` (FxChild.sol) and `FxRoot` (FxRoot.sol) are main contracts on which mapping-less bridge works. It calls and passes data to user-defined methods on another chain without mapping.

**Mumbai**

| Contract                                                                                                                | Deployed address                             |
| ----------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| [FxRoot (Goerli)](https://goerli.etherscan.io/address/0x3d1d3E34f7fB6D26245E6640E1c50710eFFf15bA#code)                  | `0x3d1d3E34f7fB6D26245E6640E1c50710eFFf15bA` |
| [FxChild (Mumbai)](https://explorer-mumbai.maticvigil.com/address/0xCf73231F28B7331BBe3124B907840A94851f9f11/contracts) | `0xCf73231F28B7331BBe3124B907840A94851f9f11` |



**Mainnet**

| Contract                                                                                                                         | Deployed address                             |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| [FxRoot (Ethereum Mainnet)](https://etherscan.io/address/0xfe5e5d361b2ad62c541bab87c45a0b9b018389a2#code)                        | `0xfe5e5D361b2ad62c541bAb87C45a0B9B018389a2` |
| [FxChild (Matic Mainnnet)](https://explorer-mainnet.maticvigil.com/address/0x8397259c983751DAf40400790063935a11afa28a/contracts) | `0x8397259c983751DAf40400790063935a11afa28a` |

You can deploy your own `FxChild` and `FxRoot`, but no need. Except you want to have some fun and have extra ETH to throw away.

#### What can I build with it?

* Arbitrary state bridge (examples/state-transfer)
* Normal ERC20 bridge (examples/erc2-transfer)
* ERC20 token generator bridge (example/mintable-erc20-transfer)
