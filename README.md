# Trusted crypto asset

A trust framework powering regulated crypto assets\
By: NYMLAB\
Date: July 2022

## Overview

Below is a diagram that outlines the key components of a proposed design pattern for creation and sustainability of regulated crypto assets.

![Trusted Crypto Asset Scheme](https://user-images.githubusercontent.com/96119806/182612857-9eeb91b0-bbfb-4156-9a76-385f53ad00bb.svg)


## Roles

### Originator

In order to originate a regulated token that can fully leverage on the technological innovation of “trustless” peer to peer transactions executed in a public decentralised network

* the legal entity originating the crypto asset must comply with regulatory licensing, risk and capital reserve requirements
* the token logic must be consistent with the smart contract based standards for fungible, non fungible and composite token structures (i.e. 20, 721, 1155)
* the minters of stable coins must provide real-time third party auditing of fiat reserves  
* policies and procedures regarding the management of fraud-prevention, AML risk on suspected accounts (freeze / unfreeze of funds) must be in place
* a continuous IT security auditing of the mint/burn infrastructure must be assured

### Holder

To be considered regulated, a Crypto Asset needs to satisfy regulatory constraints regarding their holders. 
These constraints may vary on the basis of the Crypto Asset specific nature, but we assume that a set of minimal requirements should be met, like proving that the holder has successfully carried out KYC and AML checks with an ascertainable trusted third party.
Decentralised identity and SSI protocols allow us to tread a narrow path that combines the user's right to privacy/anonymity with the possibility of on-chain verification that he or she has successfully, and without revocation, passed KYC and AML checks.
Further on, EU is on the verge of new rules (eIDAS2) and technical standards (ETSI) regarding the user wallets; in this regard, SSI provides us with the chance to inject in the transaction itself all the proofs needed to continuously validate the wallet compliance.
Finally one important client-side technical requirement is the binding between the holder and the verifiable credential stored in the wallet; currently, this feature may be achieved through the adoption of anonymous credential technology.

### Network

A sustainable proof of stake network, that provides token holders with the possibility to delegate their tokens and contribute to the network’s TVL in exchange of an APR, needs to comply with a number of regulatory constraints
Know your validator 

* a crypto asset holder who decides to delegate value to a specific validator must reach an established level of assurance and accountability threshold 
* the mass adoption of decentralised technologies does not eliminate the need to protect the investor [token holder] willing to invest [stake] their crypto value with a validator
* standard investor protection rules require moving beyond the concept of a 'trustless' network in favour of an ‘accountable’ network, where the value at stake [TVL] cease to be the defining security metrics, rather, the continuous and transparent process of verification of valid legal requirements and operational soundness become the minimum guarantee threshold

## Utility components

### Trusted Issuers

Trusted Issuers of Verifiable Credentials are instrumental to a decentralised trust framework. 
Trusted Issuers define a decentralised trust framework
* It’s up to the network underlying community (DAO) to establish and maintain the principles [requirements and constraints] regarding the trustability of assertions [VCs and proofs] based on the ascertainability of their Trusted Issuers.
* The set of Trusted Issuers may be generally defined [eIDAS Trust Service Provider List] or locally specified, eventually inheriting the general available entities and integrating the set with specific third parties. 
* Most importantly, the shift from a federated identity schemas (like SAML, Oauth2 and OIDC) where synchronous interaction with the identity provider is required, SSI allows for a full peer-to-peer interaction between the (credential) holder and the verifier.

### Trusted credential Schemas and definitions

Once defined the set of issuers that may be considered trusted by a verifier when presented with a verifiable proof derived from one or more credentials, the other founding element of a decentralised trust framework is the type and template structure of the assertions that the issuers (and the verifiers) agree upon to reach full interoperability and completion of information.
This can be achieve:
* At Domain/Community/DAO level, where all the participant, through a voting mechanism achieve consensus around a specified list of credential schemas
* At verifier Level, where the single entity can decide to shape its own trusted set of credential, eventually integrating the community-based list

### Dispute resolution procedure

The organisation of a community around a set of principles and tools set the basis to elaborate a strategies regarding accountability, liability of different roles (verifiers, holders, issuers, daos) and help in defining dispute resolution strategies, as a pragmatic approach in the wait for a broaden regulation.
Initiatives like identrust have demonstrated that this approach is feasible and may benefit the community, introducing the necessary legal components to support operation from a business standpoint.
In concrete, the procedure should be based on a set of standardized technical evidences that the involved parties may bring on in a dispute, like for instance:
* Proof, as an issuer, to comply to the community established set of protocols to be followed while evaluating a holder request to issue a specific type of credentials
* Issuer due diligence in case of credential revocation (proofs regarding the internal process to manage the revocation request, until publishing the revocation on-chain - for instance via crypto accumulator)
* Proof as a holder, to be in sole control of the credentials (for instance, credential-holder binding in case of anonymous cred)
* Verifier due diligence in case of presentation request protocol and proofs of non revocation checks

## Legal Architecture

The diagram below represents the general perspective of a decentralised trust network that we believe is necessary for a crypto asset to be regulated, and it summarises the relations existing among all components.

![LegalArchitecture](https://user-images.githubusercontent.com/96119806/182809904-c5b38f42-38dc-4df5-87ca-73fb545deca3.svg)

## Requirements

* Mandatory: Verifiable proof must be verifiable by any third party looking at the chain (and particularly to the proxy wallet holding the Trusted Crypto Asset)
* Mandatory: Verifiable proof must be derived by a (or a set of) Verifiable Credential(s) controlled by the User local account (the one controlling Vectis) - Credentials are - always - off chain
* Mandatory: Verifiable Proof must not disclose any PII of the User, apart from pseudonyms information
* Mandatory: Verifiable Proof must prove:
    - The User has received a (set of) Verifiable Credential(s) of a specific type (credential schema)
    - The User has received the (set of) Verifiable Credential(s) from one (or more) Issuer(s) included in a List of Trusted Issuers and only eligible third parties should be able to look up the real Issuer public DID
* Mandatory: any third party must be able to check for revocation of the Verifiable Credentials from which the Proof has been derived

