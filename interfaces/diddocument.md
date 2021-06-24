[Mattr Wallet SDK React Native](../README.md) / [Exports](../modules.md) / DidDocument

# Interface: DidDocument

Interface for Decentralized Identifier Document

**`see`** https://w3c-ccg.github.io/did-spec/#did-documents

## Indexable

▪ [key: `string`]: `any`

Allows for extension fields to be added to the DID Document

**`see`** https://w3c.github.io/did-core/#extensibility

## Table of contents

### Properties

- [@context](diddocument.md#@context)
- [authentication](diddocument.md#authentication)
- [created](diddocument.md#created)
- [id](diddocument.md#id)
- [keyAgreement](diddocument.md#keyagreement)
- [proof](diddocument.md#proof)
- [publicKey](diddocument.md#publickey)
- [service](diddocument.md#service)
- [updated](diddocument.md#updated)

## Properties

### @context

• `Readonly` **@context**: `JsonLdContext`

The standard context for this DID document.

**`see`** https://w3c-ccg.github.io/did-spec/#contexts

___

### authentication

• `Optional` `Readonly` **authentication**: readonly (`string` \| `object`)[]

Array of authentication methods.

**`see`** https://w3c-ccg.github.io/did-spec/#authentication

___

### created

• `Optional` `Readonly` **created**: `string`

Created date time

**`see`** https://w3c-ccg.github.io/did-spec/#created-optional

___

### id

• `Readonly` **id**: `string`

The DID for this DID document.

**`see`** https://w3c-ccg.github.io/did-spec/#did-subject

___

### keyAgreement

• `Optional` `Readonly` **keyAgreement**: readonly `unknown`[]

Used to express verification relationships

**`see`** https://w3c.github.io/did-core/#keyagreement

___

### proof

• `Optional` `Readonly` **proof**: `DidDocumentProof`

Cryptographic proof of the integrity of this DID document

**`see`** https://w3c-ccg.github.io/did-spec/#proof-optional

___

### publicKey

• `Optional` `Readonly` **publicKey**: readonly `DidDocumentPublicKey`[]

Array of public keys associated with the DID.

**`see`** https://w3c-ccg.github.io/did-spec/#public-keys

___

### service

• `Optional` `Readonly` **service**: readonly `DidDocumentService`[]

Array of services associated with the DID.

**`see`** https://w3c-ccg.github.io/did-spec/#service-endpoints

___

### updated

• `Optional` `Readonly` **updated**: `string`

Updated date time

**`see`** https://w3c-ccg.github.io/did-spec/#updated-optional
