[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / Credential

# Interface: Credential

## Indexable

▪ [key: `string`]: `any`

## Table of contents

### Properties

- [@context](credential.md#@context)
- [credentialStatus](credential.md#credentialstatus)
- [credentialSubject](credential.md#credentialsubject)
- [expirationDate](credential.md#expirationdate)
- [issuanceDate](credential.md#issuancedate)
- [issuer](credential.md#issuer)
- [type](credential.md#type)

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

• `Readonly` **credentialSubject**: `string` \| [CredentialSubject](credentialsubject.md) \| readonly [CredentialSubject](credentialsubject.md)[]

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

• `Readonly` **issuer**: [CredentialIssuer](../modules.md#credentialissuer)

**`see`** https://www.w3.org/TR/vc-data-model/#issuer

___

### type

• `Readonly` **type**: `string` \| readonly `string`[]

**`see`** https://www.w3.org/TR/vc-data-model/#types
