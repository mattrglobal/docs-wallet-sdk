[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / Credential

# Interface: Credential

## Indexable

▪ [key: `string`]: `any`

## Table of contents

### Properties

- [@context](Credential.md#@context)
- [credentialStatus](Credential.md#credentialstatus)
- [credentialSubject](Credential.md#credentialsubject)
- [expirationDate](Credential.md#expirationdate)
- [issuanceDate](Credential.md#issuancedate)
- [issuer](Credential.md#issuer)
- [type](Credential.md#type)

## Properties

### @context

• `Readonly` **@context**: `JsonLdContext`

JSON-LD @context property

first item must be a uri with the value `https://www.w3.org/2018/credentials/v1`

**`see`** https://www.w3.org/TR/vc-data-model/#contexts

___

### credentialStatus

• `Optional` `Readonly` **credentialStatus**: `CredentialStatus`

**`see`** https://www.w3.org/TR/vc-data-model/#status

___

### credentialSubject

• `Readonly` **credentialSubject**: `string` \| [`CredentialSubject`](CredentialSubject.md) \| readonly [`CredentialSubject`](CredentialSubject.md)[]

**`see`** https://www.w3.org/TR/vc-data-model/#credential-subject

___

### expirationDate

• `Optional` `Readonly` **expirationDate**: `string`

**`see`** https://www.w3.org/TR/vc-data-model/#expiration

___

### issuanceDate

• `Readonly` **issuanceDate**: `string`

**`see`** https://www.w3.org/TR/vc-data-model/#issuance-date

___

### issuer

• `Readonly` **issuer**: [`CredentialIssuer`](../modules.md#credentialissuer)

**`see`** https://www.w3.org/TR/vc-data-model/#issuer

___

### type

• `Readonly` **type**: `string` \| readonly `string`[]

**`see`** https://www.w3.org/TR/vc-data-model/#types
