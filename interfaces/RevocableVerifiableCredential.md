[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / RevocableVerifiableCredential

# Interface: RevocableVerifiableCredential

## Hierarchy

- [`VerifiableCredential`](../modules.md#verifiablecredential)

  ↳ **`RevocableVerifiableCredential`**

## Table of contents

### Properties

- [@context](RevocableVerifiableCredential.md#@context)
- [credentialStatus](RevocableVerifiableCredential.md#credentialstatus)
- [credentialSubject](RevocableVerifiableCredential.md#credentialsubject)
- [expirationDate](RevocableVerifiableCredential.md#expirationdate)
- [id](RevocableVerifiableCredential.md#id)
- [issuanceDate](RevocableVerifiableCredential.md#issuancedate)
- [issuer](RevocableVerifiableCredential.md#issuer)
- [proof](RevocableVerifiableCredential.md#proof)
- [type](RevocableVerifiableCredential.md#type)

## Properties

### @context

• `Readonly` **@context**: `JsonLdContext`

JSON-LD

**`Context`**

property

first item must be a uri with the value `https://www.w3.org/2018/credentials/v1`

**`See`**

https://www.w3.org/TR/vc-data-model/#contexts

#### Inherited from

VerifiableCredential.@context

___

### credentialStatus

• `Readonly` **credentialStatus**: `RevocationList2020CredentialStatus`

#### Overrides

VerifiableCredential.credentialStatus

___

### credentialSubject

• `Readonly` **credentialSubject**: `string` \| [`CredentialSubject`](CredentialSubject.md) \| readonly [`CredentialSubject`](CredentialSubject.md)[]

**`See`**

https://www.w3.org/TR/vc-data-model/#credential-subject

#### Inherited from

VerifiableCredential.credentialSubject

___

### expirationDate

• `Optional` `Readonly` **expirationDate**: `string`

**`See`**

https://www.w3.org/TR/vc-data-model/#expiration

#### Inherited from

VerifiableCredential.expirationDate

___

### id

• `Optional` `Readonly` **id**: `string`

#### Inherited from

VerifiableCredential.id

___

### issuanceDate

• `Readonly` **issuanceDate**: `string`

**`See`**

https://www.w3.org/TR/vc-data-model/#issuance-date

#### Inherited from

VerifiableCredential.issuanceDate

___

### issuer

• `Readonly` **issuer**: [`CredentialIssuer`](../modules.md#credentialissuer)

**`See`**

https://www.w3.org/TR/vc-data-model/#issuer

#### Inherited from

VerifiableCredential.issuer

___

### proof

• `Readonly` **proof**: [`VerifiableCredentialProof`](VerifiableCredentialProof.md) \| readonly [`VerifiableCredentialProof`](VerifiableCredentialProof.md)[]

#### Inherited from

VerifiableCredential.proof

___

### type

• `Readonly` **type**: `string` \| readonly `string`[]

**`See`**

https://www.w3.org/TR/vc-data-model/#types

#### Inherited from

VerifiableCredential.type
