[Mattr Wallet SDK React Native](../README.md) / [Exports](../modules.md) / RevocableVerifiableCredential

# Interface: RevocableVerifiableCredential

## Hierarchy

- [VerifiableCredential](../modules.md#verifiablecredential)

  ↳ **RevocableVerifiableCredential**

## Table of contents

### Properties

- [@context](revocableverifiablecredential.md#@context)
- [credentialStatus](revocableverifiablecredential.md#credentialstatus)
- [credentialSubject](revocableverifiablecredential.md#credentialsubject)
- [expirationDate](revocableverifiablecredential.md#expirationdate)
- [id](revocableverifiablecredential.md#id)
- [issuanceDate](revocableverifiablecredential.md#issuancedate)
- [issuer](revocableverifiablecredential.md#issuer)
- [proof](revocableverifiablecredential.md#proof)
- [type](revocableverifiablecredential.md#type)

## Properties

### @context

• `Readonly` **@context**: `JsonLdContext`

JSON-LD @context property

first item must be a uri with the value `https://www.w3.org/2018/credentials/v1`

**`see`** https://www.w3.org/TR/vc-data-model/#contexts

#### Inherited from

VerifiableCredential.@context

___

### credentialStatus

• `Readonly` **credentialStatus**: `RevocationList2020CredentialStatus`

#### Overrides

VerifiableCredential.credentialStatus

___

### credentialSubject

• `Readonly` **credentialSubject**: `string` \| [CredentialSubject](credentialsubject.md) \| readonly [CredentialSubject](credentialsubject.md)[]

**`see`** https://www.w3.org/TR/vc-data-model/#credential-subject

#### Inherited from

VerifiableCredential.credentialSubject

___

### expirationDate

• `Optional` `Readonly` **expirationDate**: `string`

**`see`** https://www.w3.org/TR/vc-data-model/#expiration

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

**`see`** https://www.w3.org/TR/vc-data-model/#issuance-date

#### Inherited from

VerifiableCredential.issuanceDate

___

### issuer

• `Readonly` **issuer**: [CredentialIssuer](../modules.md#credentialissuer)

**`see`** https://www.w3.org/TR/vc-data-model/#issuer

#### Inherited from

VerifiableCredential.issuer

___

### proof

• `Readonly` **proof**: [VerifiableCredentialProof](verifiablecredentialproof.md) \| readonly [VerifiableCredentialProof](verifiablecredentialproof.md)[]

#### Inherited from

VerifiableCredential.proof

___

### type

• `Readonly` **type**: `string` \| readonly `string`[]

**`see`** https://www.w3.org/TR/vc-data-model/#types

#### Inherited from

VerifiableCredential.type
