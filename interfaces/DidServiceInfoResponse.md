[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / DidServiceInfoResponse

# Interface: DidServiceInfoResponse

## Table of contents

### Properties

- [didDocument](DidServiceInfoResponse.md#diddocument)
- [localMetadata](DidServiceInfoResponse.md#localmetadata)
- [rawError](DidServiceInfoResponse.md#rawerror)
- [registrationStatus](DidServiceInfoResponse.md#registrationstatus)

## Properties

### didDocument

• `Optional` `Readonly` **didDocument**: [`DidDocument`](DidDocument.md)

The resolved DID document.

___

### localMetadata

• `Optional` `Readonly` **localMetadata**: `DidMetadata`

Local metadata for the resolved DID document.

___

### rawError

• `Optional` `Readonly` **rawError**: `Error`

Error that occurred during did resolution

___

### registrationStatus

• `Readonly` **registrationStatus**: `RegistrationStatus`

DID document registration state
