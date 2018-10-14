# validator-security

## About this repo
This repo is intended to be a collaborative effort for creating good practice guidelines for managing the security of blockchain validator nodes. The hope is that the community will come together and improve this repo by sharing knowledge and experience. At the moment it should be considered as a work in progress.

The overview idea is to provide generic security recommendations for validators on any blockchain network, but also to contain specific details on the main chains of interest to the community (e.g. Ethereum, Cosmos, Polkadot).

# Repo Structure
This repo is structured around the important domains of managing validator security. Most of the content shall be upon the aspects of security that node operators ("users") can control. It is also worth noting that there are some aspects of validator security that are specified by the protocol of the chosen network, while there may not be much that a user can do to change those parameters they will inform design choices.

User managed:
* [Physical](https://github.com/w3f/validator-security/blob/master/physical.md)
* [Operational](https://github.com/w3f/validator-security/blob/master/operational.md)
* Network (local)
* Device
* Software
* Key Management

Specified by the protocol:
* Consensus
* Economic
* Governance

Each of the above will be explored in their own document within this repo.

# What are validators?
In order to provide security guidance it is necessary to understand the role that validators play within a network and how they operate. Once we establish the most important functionality of validators then we can provide specific guidance on how to ensure that validators can perform the functionality as intended.

Let's consider two definitions from a couple of the leading networks:

**Cosmos**:
> "Validators are responsible for committing new blocks and ensuring that consensus is reached."

Sources: [1](https://cosmos.network/), [2](https://cosmos.network/docs/validators/overview.html#introduction)

**Polkadot**:
> "Validators secure the relay chain by staking DOTs, validating proofs from collators and participating in consensus with other validators."

Sources: [1](https://polkadot.network), [2](https://github.com/paritytech/polkadot/wiki/Polkadot-Roles-&-Actors)

Despite a difference in details, there is a symmetry in the roles that validators play in both the Cosmos and Polkadot networks. From the above quotations, we can understand that protocol level security rests upon validators signing a message to indicate that a particular block is correct. Once enough validators agree upon a block it is said to be final and can be committed to the relevant chain.

The signing of blocks requires the use of a private (signing) key to be held on the validator node, which requires nodes to be secure-by-default. This is what makes validation in PoS more management intensive. Validation for PoW blockchains has far fewer security requirements. The private keys for the wallets can be held on a different machine and only the public key had to be included in blocks.

Ultimately, it is the **process of message signing that we wish to make as secure as possible.**



# Considerations
While worrying about the confidentiality of the signing key is the top priority, there are other considerations that need to factor in the design and management of validator nodes.

## Economic Security
Validators are economically incentivised to behave honestly, but they are also punished for being faulty or malicious ("Byzantine"). In the former they are rewarded with tokens and in the latter their stakes are 'slashed'.

## Availability Guarantees
In addition to ensuring that the signing key is well protected, the validator node must guarantee their availability to sign new blocks. A loss in service can result in their stake being slashed.

## Nominated Proof-of-Stake
In nominated (or delegated) Proof-of-Stake it isn't necessary to have tokens 'attached' to the signing key that resides upon the validator node. An offline key could nominate their stake to a 'hot' key that resides on the node. This may make the task of managing security far easier.

This won't necessarily be true for all PoS blockchains.

## Spectrum of security postures
There could be a spectrum of validator nodes, such that nodes won't be required to have the same level of security. Nodes of a lower level of security would have less importance within the network but they also probably require less stake. The consequence is that asking all validator nodes to have enterprise grade security is unnecessary.
