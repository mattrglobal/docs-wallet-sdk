[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / KeyManagementService

# Interface: KeyManagementService

Defines the interface of the KMS interface

## Table of contents

### Methods

- [close](KeyManagementService.md#close)
- [decrypt](KeyManagementService.md#decrypt)
- [deleteKey](KeyManagementService.md#deletekey)
- [deriveKey](KeyManagementService.md#derivekey)
- [digest](KeyManagementService.md#digest)
- [encrypt](KeyManagementService.md#encrypt)
- [exportKey](KeyManagementService.md#exportkey)
- [generateKey](KeyManagementService.md#generatekey)
- [generateRandom](KeyManagementService.md#generaterandom)
- [getKeyInfo](KeyManagementService.md#getkeyinfo)
- [sign](KeyManagementService.md#sign)
- [unWrapKey](KeyManagementService.md#unwrapkey)
- [verify](KeyManagementService.md#verify)
- [wrapKey](KeyManagementService.md#wrapkey)

## Methods

### close

▸ `Readonly` **close**(): `Promise`<`void`\>

Close and release resources

#### Returns

`Promise`<`void`\>

Promise resolving and return nothing

___

### decrypt

▸ `Readonly` **decrypt**(`decryptOptions`): `Promise`<`Uint8Array`\>

Takes in the necessary data to be decrypted

#### Parameters

| Name | Type |
| :------ | :------ |
| `decryptOptions` | `EncryptionOptions` |

#### Returns

`Promise`<`Uint8Array`\>

unencoded plaintext data

___

### deleteKey

▸ `Readonly` **deleteKey**(`keyId`): `Promise`<`undefined` \| `KeyInfo`\>

Deletes a key by keyId

#### Parameters

| Name | Type |
| :------ | :------ |
| `keyId` | `string` |

#### Returns

`Promise`<`undefined` \| `KeyInfo`\>

a KeyInfo object of the KeyId if found

___

### deriveKey

▸ `Readonly` **deriveKey**(`deriveKeyOptions`): `Promise`<`KeyInfo`\>

Derives a key and stores it in the KMS

#### Parameters

| Name | Type |
| :------ | :------ |
| `deriveKeyOptions` | `DeriveKeyOptions` |

#### Returns

`Promise`<`KeyInfo`\>

A keyInfo object of the key stored in the KMS

___

### digest

▸ `Readonly` **digest**(`algorithm`, `data`): `Promise`<`Uint8Array`\>

Generates a hash digest of the data

#### Parameters

| Name | Type |
| :------ | :------ |
| `algorithm` | `DigestAlgorithm` |
| `data` | `Uint8Array` |

#### Returns

`Promise`<`Uint8Array`\>

a hash digest

___

### encrypt

▸ `Readonly` **encrypt**(`encryptOptions`): `Promise`<`EncryptionResult`\>

Takes in the necessary data to encrypt

#### Parameters

| Name | Type |
| :------ | :------ |
| `encryptOptions` | `EncryptionOptions` |

#### Returns

`Promise`<`EncryptionResult`\>

unencoded ciphertext data

___

### exportKey

▸ `Readonly` **exportKey**(`keyId`): `Promise`<`undefined` \| `Uint8Array`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `keyId` | `string` |

#### Returns

`Promise`<`undefined` \| `Uint8Array`\>

a RAW secret, if key exists. If key isn't extractable, throws Error

___

### generateKey

▸ `Readonly` **generateKey**(`generateKeyOptions`): `Promise`<`KeyInfo`\>

Generates a key and stores it in the KMS

#### Parameters

| Name | Type |
| :------ | :------ |
| `generateKeyOptions` | `GenerateKeyOptions` |

#### Returns

`Promise`<`KeyInfo`\>

a reference id to a newly generated key that's store in the KMS

___

### generateRandom

▸ `Readonly` **generateRandom**(`size`): `Promise`<`Uint8Array`\>

Generates an array of random bytes using a Cryptographically Secure Pseudo Random Number Generator (CSPRNG)

#### Parameters

| Name | Type |
| :------ | :------ |
| `size` | `number` |

#### Returns

`Promise`<`Uint8Array`\>

an array of pseudo random bytes

___

### getKeyInfo

▸ `Readonly` **getKeyInfo**(`keyId`): `Promise`<`undefined` \| `KeyInfo`\>

Defines the parameters for getKeyInfo function interface into an object type

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `keyId` | `string` | The identifier of the key |

#### Returns

`Promise`<`undefined` \| `KeyInfo`\>

a KeyInfo object of the KeyId

___

### sign

▸ `Readonly` **sign**(`signOptions`): `Promise`<`Uint8Array`\>

Signs a message provided as input

#### Parameters

| Name | Type |
| :------ | :------ |
| `signOptions` | `SignOptions` |

#### Returns

`Promise`<`Uint8Array`\>

signature of the data

___

### unWrapKey

▸ `Readonly` **unWrapKey**(`UnWrapKeyOptions`): `Promise`<`KeyInfo`\>

Un-wraps a key and stores it in the KMS

#### Parameters

| Name | Type |
| :------ | :------ |
| `UnWrapKeyOptions` | `UnWrapKeyOptions` |

#### Returns

`Promise`<`KeyInfo`\>

Key info of the un-wrapped key

___

### verify

▸ `Readonly` **verify**(`verifyOptions`): `Promise`<`boolean`\>

Verifies a signature

#### Parameters

| Name | Type |
| :------ | :------ |
| `verifyOptions` | `VerifyOptions` |

#### Returns

`Promise`<`boolean`\>

true if the signature is valid else false

___

### wrapKey

▸ `Readonly` **wrapKey**(`WrapKeyOptions`): `Promise`<`EncryptionResult`\>

Wraps a key and returns it

#### Parameters

| Name | Type |
| :------ | :------ |
| `WrapKeyOptions` | `WrapKeyOptions` |

#### Returns

`Promise`<`EncryptionResult`\>

unencoded ciphertext data
