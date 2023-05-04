[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / codec

# Namespace: codec

## Table of contents

### Type Aliases

- [DeflateError](codec.md#deflateerror)
- [InflateError](codec.md#inflateerror)
- [InvalidBase32DecodeError](codec.md#invalidbase32decodeerror)
- [InvalidBase64DecodeError](codec.md#invalidbase64decodeerror)
- [InvalidBase64URLDecodeError](codec.md#invalidbase64urldecodeerror)
- [InvalidCborldDecodeError](codec.md#invalidcborlddecodeerror)
- [InvalidCborldEncodeError](codec.md#invalidcborldencodeerror)
- [InvalidJSONError](codec.md#invalidjsonerror)
- [MultiHash](codec.md#multihash)
- [MultiHashError](codec.md#multihasherror)

### Variables

- [MultiHash](codec.md#multihash-1)

### Functions

- [base32Decode](codec.md#base32decode)
- [base32DecodeToString](codec.md#base32decodetostring)
- [base32Encode](codec.md#base32encode)
- [base32EncodeFromString](codec.md#base32encodefromstring)
- [base64Decode](codec.md#base64decode)
- [base64DecodeToString](codec.md#base64decodetostring)
- [base64Encode](codec.md#base64encode)
- [base64EncodeFromString](codec.md#base64encodefromstring)
- [base64UrlDecode](codec.md#base64urldecode)
- [base64UrlDecodeToObject](codec.md#base64urldecodetoobject)
- [base64UrlEncode](codec.md#base64urlencode)
- [base64UrlEncodeFromObject](codec.md#base64urlencodefromobject)
- [base64UrlEncodeFromString](codec.md#base64urlencodefromstring)
- [base64UrlEncodeNoPadding](codec.md#base64urlencodenopadding)
- [bytesToString](codec.md#bytestostring)
- [canonicalMultiHash](codec.md#canonicalmultihash)
- [decodeCborld](codec.md#decodecborld)
- [deflate](codec.md#deflate)
- [encodeCborld](codec.md#encodecborld)
- [inflate](codec.md#inflate)
- [stringToBytes](codec.md#stringtobytes)

## Type Aliases

### DeflateError

Ƭ **DeflateError**: `DeflateError`

___

### InflateError

Ƭ **InflateError**: `InflateError`

___

### InvalidBase32DecodeError

Ƭ **InvalidBase32DecodeError**: `InvalidBase32DecodeError`

___

### InvalidBase64DecodeError

Ƭ **InvalidBase64DecodeError**: `InvalidBase64DecodeError`

___

### InvalidBase64URLDecodeError

Ƭ **InvalidBase64URLDecodeError**: [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror)

___

### InvalidCborldDecodeError

Ƭ **InvalidCborldDecodeError**: `InvalidCborldDecodeError`

___

### InvalidCborldEncodeError

Ƭ **InvalidCborldEncodeError**: `InvalidCborldEncodeError`

___

### InvalidJSONError

Ƭ **InvalidJSONError**: [`InvalidJSONError`](../modules.md#invalidjsonerror)

___

### MultiHash

Ƭ **MultiHash**: `MultiHash`

___

### MultiHashError

Ƭ **MultiHashError**: `MultiHashError`

## Variables

### MultiHash

• **MultiHash**: typeof `MultiHash`

## Functions

### base32Decode

▸ **base32Decode**(`base32String`): [`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase32DecodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base32String` | `string` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase32DecodeError`\>

___

### base32DecodeToString

▸ **base32DecodeToString**(`base32String`): [`Result`](../modules.md#result)<`string`, `InvalidBase32DecodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base32String` | `string` |

#### Returns

[`Result`](../modules.md#result)<`string`, `InvalidBase32DecodeError`\>

___

### base32Encode

▸ **base32Encode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base32EncodeFromString

▸ **base32EncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64Decode

▸ **base64Decode**(`base64String`): [`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase64DecodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase64DecodeError`\>

___

### base64DecodeToString

▸ **base64DecodeToString**(`base64String`): [`Result`](../modules.md#result)<`string`, `InvalidBase64DecodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

#### Returns

[`Result`](../modules.md#result)<`string`, `InvalidBase64DecodeError`\>

___

### base64Encode

▸ **base64Encode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base64EncodeFromString

▸ **base64EncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64UrlDecode

▸ **base64UrlDecode**(`base64urlString`): [`Result`](../modules.md#result)<`Uint8Array`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64urlString` | `string` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror)\>

___

### base64UrlDecodeToObject

▸ **base64UrlDecodeToObject**(`base64urlString`): [`Result`](../modules.md#result)<`object`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror) \| [`InvalidJSONError`](../modules.md#invalidjsonerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64urlString` | `string` |

#### Returns

[`Result`](../modules.md#result)<`object`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror) \| [`InvalidJSONError`](../modules.md#invalidjsonerror)\>

___

### base64UrlEncode

▸ **base64UrlEncode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base64UrlEncodeFromObject

▸ **base64UrlEncodeFromObject**(`obj`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `obj` | `Record`<`string`, `unknown`\> |

#### Returns

`string`

___

### base64UrlEncodeFromString

▸ **base64UrlEncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64UrlEncodeNoPadding

▸ **base64UrlEncodeNoPadding**(`bytes`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `bytes` | `Uint8Array` |

#### Returns

`string`

___

### bytesToString

▸ **bytesToString**(`bytes`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `bytes` | `Uint8Array` |

#### Returns

`string`

___

### canonicalMultiHash

▸ **canonicalMultiHash**(`input`, `hashAlgorithm`): [`Result`](../modules.md#result)<`Uint8Array`, `MultiHashError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `Record`<`string`, `unknown`\> |
| `hashAlgorithm` | `Sha256` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `MultiHashError`\>

___

### decodeCborld

▸ **decodeCborld**(`byteArray`, `documentLoader`): `ResultAsync`<`unknown`, `InvalidCborldDecodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |
| `documentLoader` | `DocumentLoader` |

#### Returns

`ResultAsync`<`unknown`, `InvalidCborldDecodeError`\>

___

### deflate

▸ **deflate**(`data`): [`Result`](../modules.md#result)<`Uint8Array`, `DeflateError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `Uint8Array` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `DeflateError`\>

___

### encodeCborld

▸ **encodeCborld**(`jsonldDocument`, `documentLoader`): `ResultAsync`<`Uint8Array`, `InvalidCborldEncodeError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `jsonldDocument` | `Record`<`string`, `unknown`\> |
| `documentLoader` | `DocumentLoader` |

#### Returns

`ResultAsync`<`Uint8Array`, `InvalidCborldEncodeError`\>

___

### inflate

▸ **inflate**(`data`): [`Result`](../modules.md#result)<`Uint8Array`, `InflateError`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `Uint8Array` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InflateError`\>

___

### stringToBytes

▸ **stringToBytes**(`str`): `Uint8Array`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`Uint8Array`
