[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / DidDocument

# Interface: DidDocument

Interface for Decentralized Identifier Document

**`See`**

https://w3c-ccg.github.io/did-spec/#did-documents

## Indexable

▪ [key: `string`]: `any`

## Table of contents

### Properties

- [@context](DidDocument.md#@context)
- [assertionMethod](DidDocument.md#assertionmethod)
- [authentication](DidDocument.md#authentication)
- [created](DidDocument.md#created)
- [id](DidDocument.md#id)
- [keyAgreement](DidDocument.md#keyagreement)
- [proof](DidDocument.md#proof)
- [service](DidDocument.md#service)
- [updated](DidDocument.md#updated)
- [verificationMethod](DidDocument.md#verificationmethod)

## Properties

### @context

• `Readonly` **@context**: `JsonLdContext`

The standard context for this DID document.

**`See`**

https://w3c-ccg.github.io/did-spec/#contexts

___

### assertionMethod

• `Optional` `Readonly` **assertionMethod**: readonly `string`[] \| readonly `DidDocumentPublicKey`[]

Used to express assertion method

**`See`**

https://w3c.github.io/did-core/#assertion

___

### authentication

• `Optional` `Readonly` **authentication**: readonly (`string` \| `object`)[]

Array of authentication methods.

**`See`**

https://w3c-ccg.github.io/did-spec/#authentication

___

### created

• `Optional` `Readonly` **created**: `string`

Created date time

**`See`**

https://w3c-ccg.github.io/did-spec/#created-optional

___

### id

• `Readonly` **id**: `string`

The DID for this DID document.

**`See`**

https://w3c-ccg.github.io/did-spec/#did-subject

___

### keyAgreement

• `Optional` `Readonly` **keyAgreement**: readonly `unknown`[]

Used to express verification relationships

**`See`**

https://w3c.github.io/did-core/#keyagreement

___

### proof

• `Optional` `Readonly` **proof**: `DidDocumentProof`

Cryptographic proof of the integrity of this DID document

**`See`**

https://w3c-ccg.github.io/did-spec/#proof-optional

___

### service

• `Optional` `Readonly` **service**: readonly `DidDocumentService`[]

Array of services associated with the DID.

**`See`**

https://w3c-ccg.github.io/did-spec/#service-endpoints

___

### updated

• `Optional` `Readonly` **updated**: `string`

Updated date time

**`See`**

https://w3c-ccg.github.io/did-spec/#updated-optional

___

### verificationMethod

• `Optional` `Readonly` **verificationMethod**: readonly `DidDocumentPublicKey`[]

Used to express verification method

**`See`**

https://w3c.github.io/did-core/#verification-methods
