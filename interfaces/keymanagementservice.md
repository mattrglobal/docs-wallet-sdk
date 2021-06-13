[Mattr Wallet SDK React Native](../README.md) / [Exports](../modules.md) / KeyManagementService

# Interface: KeyManagementService

Defines the interface of the KMS interface

## Table of contents

### Properties

- [close](keymanagementservice.md#close)
- [decrypt](keymanagementservice.md#decrypt)
- [deleteKey](keymanagementservice.md#deletekey)
- [deriveKey](keymanagementservice.md#derivekey)
- [digest](keymanagementservice.md#digest)
- [encrypt](keymanagementservice.md#encrypt)
- [exportKey](keymanagementservice.md#exportkey)
- [generateKey](keymanagementservice.md#generatekey)
- [generateRandom](keymanagementservice.md#generaterandom)
- [getKeyInfo](keymanagementservice.md#getkeyinfo)
- [sign](keymanagementservice.md#sign)
- [unWrapKey](keymanagementservice.md#unwrapkey)
- [verify](keymanagementservice.md#verify)
- [wrapKey](keymanagementservice.md#wrapkey)

## Properties

### close

• `Readonly` **close**: () => `Promise`<void\>

Close and release resources

**`returns`** Promise resolving and return nothing

#### Type declaration

▸ (): `Promise`<void\>

##### Returns

`Promise`<void\>

___

### decrypt

• `Readonly` **decrypt**: (`decryptOptions`: `EncryptionOptions`) => `Promise`<Uint8Array\>

Takes in the necessary data to be decrypted

**`returns`** unencoded plaintext data

#### Type declaration

▸ (`decryptOptions`): `Promise`<Uint8Array\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `decryptOptions` | `EncryptionOptions` |

##### Returns

`Promise`<Uint8Array\>

___

### deleteKey

• `Readonly` **deleteKey**: (`keyId`: `string`) => `Promise`<undefined \| KeyInfo\>

Deletes a key by keyId

**`returns`** a KeyInfo object of the KeyId if found

#### Type declaration

▸ (`keyId`): `Promise`<undefined \| KeyInfo\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `keyId` | `string` |

##### Returns

`Promise`<undefined \| KeyInfo\>

___

### deriveKey

• `Readonly` **deriveKey**: (`deriveKeyOptions`: `DeriveKeyOptions`) => `Promise`<KeyInfo\>

Derives a key and stores it in the KMS

**`returns`** A keyInfo object of the key stored in the KMS

#### Type declaration

▸ (`deriveKeyOptions`): `Promise`<KeyInfo\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `deriveKeyOptions` | `DeriveKeyOptions` |

##### Returns

`Promise`<KeyInfo\>

___

### digest

• `Readonly` **digest**: (`algorithm`: `DigestAlgorithm`, `data`: `Uint8Array`) => `Promise`<Uint8Array\>

Generates a hash digest of the data

**`returns`** a hash digest

#### Type declaration

▸ (`algorithm`, `data`): `Promise`<Uint8Array\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `algorithm` | `DigestAlgorithm` |
| `data` | `Uint8Array` |

##### Returns

`Promise`<Uint8Array\>

___

### encrypt

• `Readonly` **encrypt**: (`encryptOptions`: `EncryptionOptions`) => `Promise`<EncryptionResult\>

Takes in the necessary data to encrypt

**`returns`** unencoded ciphertext data

#### Type declaration

▸ (`encryptOptions`): `Promise`<EncryptionResult\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `encryptOptions` | `EncryptionOptions` |

##### Returns

`Promise`<EncryptionResult\>

___

### exportKey

• `Readonly` **exportKey**: (`keyId`: `string`) => `Promise`<undefined \| Uint8Array\>

**`returns`** a RAW secret, if key exists. If key isn't extractable, throws Error

#### Type declaration

▸ (`keyId`): `Promise`<undefined \| Uint8Array\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `keyId` | `string` |

##### Returns

`Promise`<undefined \| Uint8Array\>

___

### generateKey

• `Readonly` **generateKey**: (`generateKeyOptions`: `GenerateKeyOptions`) => `Promise`<KeyInfo\>

Generates a key and stores it in the KMS

**`returns`** a reference id to a newly generated key that's store in the KMS

#### Type declaration

▸ (`generateKeyOptions`): `Promise`<KeyInfo\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `generateKeyOptions` | `GenerateKeyOptions` |

##### Returns

`Promise`<KeyInfo\>

___

### generateRandom

• `Readonly` **generateRandom**: (`size`: `number`) => `Promise`<Uint8Array\>

Generates an array of random bytes using a Cryptographically Secure Pseudo Random Number Generator (CSPRNG)

**`returns`** an array of pseudo random bytes

#### Type declaration

▸ (`size`): `Promise`<Uint8Array\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `size` | `number` |

##### Returns

`Promise`<Uint8Array\>

___

### getKeyInfo

• `Readonly` **getKeyInfo**: (`keyId`: `string`) => `Promise`<undefined \| KeyInfo\>

Defines the parameters for getKeyInfo function interface into an object type

**`param`** The identifier of the key

**`returns`** a KeyInfo object of the KeyId

#### Type declaration

▸ (`keyId`): `Promise`<undefined \| KeyInfo\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `keyId` | `string` |

##### Returns

`Promise`<undefined \| KeyInfo\>

___

### sign

• `Readonly` **sign**: (`signOptions`: `SignOptions`) => `Promise`<Uint8Array\>

Signs a message provided as input

**`returns`** signature of the data

#### Type declaration

▸ (`signOptions`): `Promise`<Uint8Array\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `signOptions` | `SignOptions` |

##### Returns

`Promise`<Uint8Array\>

___

### unWrapKey

• `Readonly` **unWrapKey**: (`UnWrapKeyOptions`: `UnWrapKeyOptions`) => `Promise`<KeyInfo\>

Un-wraps a key and stores it in the KMS

**`returns`** Key info of the un-wrapped key

#### Type declaration

▸ (`UnWrapKeyOptions`): `Promise`<KeyInfo\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `UnWrapKeyOptions` | `UnWrapKeyOptions` |

##### Returns

`Promise`<KeyInfo\>

___

### verify

• `Readonly` **verify**: (`verifyOptions`: `VerifyOptions`) => `Promise`<boolean\>

Verifies a signature

**`returns`** true if the signature is valid else false

#### Type declaration

▸ (`verifyOptions`): `Promise`<boolean\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `verifyOptions` | `VerifyOptions` |

##### Returns

`Promise`<boolean\>

___

### wrapKey

• `Readonly` **wrapKey**: (`WrapKeyOptions`: `WrapKeyOptions`) => `Promise`<EncryptionResult\>

Wraps a key and returns it

**`returns`** unencoded ciphertext data

#### Type declaration

▸ (`WrapKeyOptions`): `Promise`<EncryptionResult\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `WrapKeyOptions` | `WrapKeyOptions` |

##### Returns

`Promise`<EncryptionResult\>
