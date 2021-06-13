[Mattr Wallet SDK React Native](../README.md) / [Exports](../modules.md) / codec

# Namespace: codec

## Table of contents

### Type aliases

- [InvalidBase64URLDecodeError](codec.md#invalidbase64urldecodeerror)
- [InvalidJSONError](codec.md#invalidjsonerror)

### Functions

- [base64UrlDecode](codec.md#base64urldecode)
- [base64UrlDecodeToObject](codec.md#base64urldecodetoobject)
- [base64UrlEncode](codec.md#base64urlencode)
- [base64UrlEncodeFromObject](codec.md#base64urlencodefromobject)
- [base64UrlEncodeFromString](codec.md#base64urlencodefromstring)
- [base64UrlEncodeNoPadding](codec.md#base64urlencodenopadding)
- [bytesToString](codec.md#bytestostring)
- [stringToBytes](codec.md#stringtobytes)

## Type aliases

### InvalidBase64URLDecodeError

Ƭ **InvalidBase64URLDecodeError**: [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)

___

### InvalidJSONError

Ƭ **InvalidJSONError**: [InvalidJSONError](../modules.md#invalidjsonerror)

## Functions

### base64UrlDecode

▸ `Const` **base64UrlDecode**(`base64String`): [Result](result.md)<Uint8Array, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

#### Returns

[Result](result.md)<Uint8Array, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror)\>

___

### base64UrlDecodeToObject

▸ `Const` **base64UrlDecodeToObject**(`base64String`): [Result](result.md)<object, [InvalidBase64URLDecodeError](../modules.md#invalidbase64urldecodeerror) \| [InvalidJSONError](../modules.md#invalidjsonerror)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `base64String` | `string` |

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

### stringToBytes

▸ `Const` **stringToBytes**(`str`): `Uint8Array`

#### Parameters

| Name | Type |
| :------ | :------ |
| `str` | `string` |

#### Returns

`Uint8Array`
