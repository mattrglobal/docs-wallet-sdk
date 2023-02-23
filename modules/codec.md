[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / codec

# Namespace: codec

## Table of contents

### Type aliases

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

- [MultiHash](codec.md#multihash)

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

## Type aliases

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

Ƭ **InvalidBase64URLDecodeError**: [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)

___

### InvalidCborldDecodeError

Ƭ **InvalidCborldDecodeError**: `InvalidCborldDecodeError`

___

### InvalidCborldEncodeError

Ƭ **InvalidCborldEncodeError**: `InvalidCborldEncodeError`

___

### InvalidJSONError

Ƭ **InvalidJSONError**: [InvalidJSONError](../modules.md#invalidjsonerror)

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

▸ `Const` **base32Decode**(`base32String`): [Result](result.md)<Uint8Array, InvalidBase32DecodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base32String` | `string` |

#### Returns

[Result](result.md)<Uint8Array, InvalidBase32DecodeError\>

___

### base32DecodeToString

▸ `Const` **base32DecodeToString**(`base32String`): [Result](result.md)<string, InvalidBase32DecodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base32String` | `string` |

#### Returns

[Result](result.md)<string, InvalidBase32DecodeError\>

___

### base32Encode

▸ `Const` **base32Encode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base32EncodeFromString

▸ `Const` **base32EncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64Decode

▸ `Const` **base64Decode**(`base64String`): [Result](result.md)<Uint8Array, InvalidBase64DecodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

#### Returns

[Result](result.md)<Uint8Array, InvalidBase64DecodeError\>

___

### base64DecodeToString

▸ `Const` **base64DecodeToString**(`base64String`): [Result](result.md)<string, InvalidBase64DecodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

#### Returns

[Result](result.md)<string, InvalidBase64DecodeError\>

___

### base64Encode

▸ `Const` **base64Encode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base64EncodeFromString

▸ `Const` **base64EncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64UrlDecode

▸ `Const` **base64UrlDecode**(`base64urlString`): [Result](result.md)<Uint8Array, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64urlString` | `string` |

#### Returns

[Result](result.md)<Uint8Array, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)\>

___

### base64UrlDecodeToObject

▸ `Const` **base64UrlDecodeToObject**(`base64urlString`): [Result](result.md)<object, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror) \| [InvalidJSONError](../modules.md#invalidjsonerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64urlString` | `string` |

#### Returns

[Result](result.md)<object, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror) \| [InvalidJSONError](../modules.md#invalidjsonerror)\>

___

### base64UrlEncode

▸ `Const` **base64UrlEncode**(`byteArray`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |

#### Returns

`string`

___

### base64UrlEncodeFromObject

▸ `Const` **base64UrlEncodeFromObject**(`obj`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `obj` | `Record`<string, unknown\> |

#### Returns

`string`

___

### base64UrlEncodeFromString

▸ `Const` **base64UrlEncodeFromString**(`str`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`string`

___

### base64UrlEncodeNoPadding

▸ `Const` **base64UrlEncodeNoPadding**(`bytes`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `bytes` | `Uint8Array` |

#### Returns

`string`

___

### bytesToString

▸ `Const` **bytesToString**(`bytes`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `bytes` | `Uint8Array` |

#### Returns

`string`

___

### canonicalMultiHash

▸ `Const` **canonicalMultiHash**(`input`, `hashAlgorithm`): [Result](result.md)<Uint8Array, MultiHashError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `Record`<string, unknown\> |
| `hashAlgorithm` | `Sha256` |

#### Returns

[Result](result.md)<Uint8Array, MultiHashError\>

___

### decodeCborld

▸ `Const` **decodeCborld**(`byteArray`, `documentLoader`): `ResultAsync`<unknown, InvalidCborldDecodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `byteArray` | `Uint8Array` |
| `documentLoader` | `DocumentLoader` |

#### Returns

`ResultAsync`<unknown, InvalidCborldDecodeError\>

___

### deflate

▸ `Const` **deflate**(`data`): [Result](result.md)<Uint8Array, DeflateError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `Uint8Array` |

#### Returns

[Result](result.md)<Uint8Array, DeflateError\>

___

### encodeCborld

▸ `Const` **encodeCborld**(`jsonldDocument`, `documentLoader`): `ResultAsync`<Uint8Array, InvalidCborldEncodeError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `jsonldDocument` | `Record`<string, unknown\> |
| `documentLoader` | `DocumentLoader` |

#### Returns

`ResultAsync`<Uint8Array, InvalidCborldEncodeError\>

___

### inflate

▸ `Const` **inflate**(`data`): [Result](result.md)<Uint8Array, InflateError\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `data` | `Uint8Array` |

#### Returns

[Result](result.md)<Uint8Array, InflateError\>

___

### stringToBytes

▸ `Const` **stringToBytes**(`str`): `Uint8Array`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`Uint8Array`
