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

Ƭ **InvalidCborldDecodeError**: [`InvalidCborldDecodeError`](../modules.md#invalidcborlddecodeerror)

___

### InvalidCborldEncodeError

Ƭ **InvalidCborldEncodeError**: [`InvalidCborldEncodeError`](../modules.md#invalidcborldencodeerror)

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

Base32 decode to Uint8Array

#### Parameters

| Name | Type |
| :------ | :------ |
| `base32String` | `string` |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase32DecodeError`\>

A [Result](../modules.md#result) containing the decoded Uint8Array on ok or a [InvalidBase32DecodeError](codec.md#invalidbase32decodeerror) on error

___

### base32DecodeToString

▸ **base32DecodeToString**(`base32String`): [`Result`](../modules.md#result)<`string`, `InvalidBase32DecodeError`\>

Base32 decode to a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `base32String` | `string` | The base32 encoded string |

#### Returns

[`Result`](../modules.md#result)<`string`, `InvalidBase32DecodeError`\>

A [Result](../modules.md#result) containing the decoded string on ok or a [InvalidBase32DecodeError](codec.md#invalidbase32decodeerror)  on error

___

### base32Encode

▸ **base32Encode**(`byteArray`): `string`

Base32 encode an Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `byteArray` | `Uint8Array` | The bytes to encode |

#### Returns

`string`

The string of the encoded bytes

___

### base32EncodeFromString

▸ **base32EncodeFromString**(`str`): `string`

Base32 encode a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `str` | `string` | The string to encode |

#### Returns

`string`

The base32 encoded string

___

### base64Decode

▸ **base64Decode**(`base64String`): [`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase64DecodeError`\>

Base64 decode to Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `base64String` | `string` | The base64 encoded string |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InvalidBase64DecodeError`\>

A [Result](../modules.md#result) containing the decoded Uint8Array on ok or a [InvalidBase64DecodeError](codec.md#invalidbase64decodeerror) on error

___

### base64DecodeToString

▸ **base64DecodeToString**(`base64String`): [`Result`](../modules.md#result)<`string`, `InvalidBase64DecodeError`\>

Base64 decode to a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `base64String` | `string` | The base64 encoded string |

#### Returns

[`Result`](../modules.md#result)<`string`, `InvalidBase64DecodeError`\>

A [Result](../modules.md#result) containing the decoded string on ok or a [InvalidBase64DecodeError](codec.md#invalidbase64decodeerror) on error

___

### base64Encode

▸ **base64Encode**(`byteArray`): `string`

Base64 encode an Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `byteArray` | `Uint8Array` | The bytes to encode |

#### Returns

`string`

The string of the encoded bytes

___

### base64EncodeFromString

▸ **base64EncodeFromString**(`str`): `string`

Base64 encode a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `str` | `string` | The string to encode |

#### Returns

`string`

The base64 encoded string

___

### base64UrlDecode

▸ **base64UrlDecode**(`base64urlString`): [`Result`](../modules.md#result)<`Uint8Array`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror)\>

Base64URL decode to Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `base64urlString` | `string` | The base64url encoded string |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror)\>

A [Result](../modules.md#result) containing the decoded Uint8Array on ok or a [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror) on error

___

### base64UrlDecodeToObject

▸ **base64UrlDecodeToObject**(`base64urlString`): [`Result`](../modules.md#result)<`object`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror) \| [`InvalidJSONError`](../modules.md#invalidjsonerror)\>

Base64URL decode to an object

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `base64urlString` | `string` | The base64url encoded string |

#### Returns

[`Result`](../modules.md#result)<`object`, [`InvalidBase64URLDecodeError`](../modules.md#invalidbase64urldecodeerror) \| [`InvalidJSONError`](../modules.md#invalidjsonerror)\>

A [Result](../modules.md#result) containing the decoded object on ok or a [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror) or [InvalidJSONError](../modules.md#invalidjsonerror) on error

___

### base64UrlEncode

▸ **base64UrlEncode**(`byteArray`): `string`

Base64URL encode an Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `byteArray` | `Uint8Array` | The bytes to encode |

#### Returns

`string`

The string of the encoded bytes

___

### base64UrlEncodeFromObject

▸ **base64UrlEncodeFromObject**(`obj`): `string`

Base64URL encode an object

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `obj` | `Record`<`string`, `unknown`\> | The object to create the encoded string from |

#### Returns

`string`

The string of the encoded object

___

### base64UrlEncodeFromString

▸ **base64UrlEncodeFromString**(`str`): `string`

Base64URL encode a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `str` | `string` | The string to encode |

#### Returns

`string`

The base64url encoded string

___

### base64UrlEncodeNoPadding

▸ **base64UrlEncodeNoPadding**(`bytes`): `string`

Base64URL encode with no padding from an Uint8Array to a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bytes` | `Uint8Array` | The bytes to encode |

#### Returns

`string`

The base64url encoded string

___

### bytesToString

▸ **bytesToString**(`bytes`): `string`

Convert a Uint8Array to a string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `bytes` | `Uint8Array` | The bytes to convert to a string |

#### Returns

`string`

The string result from the converted bytes

___

### canonicalMultiHash

▸ **canonicalMultiHash**(`input`, `hashAlgorithm`): [`Result`](../modules.md#result)<`Uint8Array`, `MultiHashError`\>

Creates a canonical multihash of the input object by canonicalizing the object.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `Record`<`string`, `unknown`\> | The object to canonicalize and then hash |
| `hashAlgorithm` | `Sha256` | The algorithm to hash and encode the data with |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `MultiHashError`\>

A [Result](../modules.md#result) containing the encoded Uint8Array on ok or a [MultiHashError](codec.md#multihasherror) on error

___

### decodeCborld

▸ **decodeCborld**(`byteArray`, `documentLoader`): `ResultAsync`<`unknown`, [`InvalidCborldDecodeError`](../modules.md#invalidcborlddecodeerror)\>

Decode CBOR-LD bytes intoto JSON-LD document

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `byteArray` | `Uint8Array` | The cborld bytes |
| `documentLoader` | `DocumentLoader` | The document loader to resolve contexts |

#### Returns

`ResultAsync`<`unknown`, [`InvalidCborldDecodeError`](../modules.md#invalidcborlddecodeerror)\>

A ResultAsync containing the decoded object on ok or a [InvalidCborldDecodeError](../modules.md#invalidcborlddecodeerror) on error

___

### deflate

▸ **deflate**(`data`): [`Result`](../modules.md#result)<`Uint8Array`, `DeflateError`\>

Deflate compression

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Uint8Array` | The data to be compressed |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `DeflateError`\>

A [Result](../modules.md#result) containing the compressed Uint8Array on ok or a [DeflateError](codec.md#deflateerror) on error

___

### encodeCborld

▸ **encodeCborld**(`jsonldDocument`, `documentLoader`): `ResultAsync`<`Uint8Array`, [`InvalidCborldEncodeError`](../modules.md#invalidcborldencodeerror)\>

Encode a JSON-LD document into CBOR-LD bytes

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `jsonldDocument` | `Record`<`string`, `unknown`\> | The json document to encode |
| `documentLoader` | `DocumentLoader` | The document loader to resolve contexts |

#### Returns

`ResultAsync`<`Uint8Array`, [`InvalidCborldEncodeError`](../modules.md#invalidcborldencodeerror)\>

A ResultAsync containing the decoded cborld bytes on ok or a [InvalidCborldEncodeError](../modules.md#invalidcborldencodeerror) on error

___

### inflate

▸ **inflate**(`data`): [`Result`](../modules.md#result)<`Uint8Array`, `InflateError`\>

Inflate decompression

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `data` | `Uint8Array` | The data to be decompressed |

#### Returns

[`Result`](../modules.md#result)<`Uint8Array`, `InflateError`\>

A [Result](../modules.md#result) containing the decompressed Uint8Array on ok or a [InflateError](codec.md#inflateerror) on error

___

### stringToBytes

▸ **stringToBytes**(`str`): `Uint8Array`

Convert a string to an Uint8Array

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `str` | `string` | The string to convert to bytes |

#### Returns

`Uint8Array`

The bytes result from the converted string
