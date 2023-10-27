[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / DidService

# Interface: DidService

## Table of contents

### Properties

- [create](DidService.md#create)
- [delete](DidService.md#delete)
- [dereference](DidService.md#dereference)
- [info](DidService.md#info)
- [list](DidService.md#list)

## Properties

### create

• `Readonly` **create**: (`request`: `DidServiceCreateRequest`) => `Promise`<`DidServiceCreateResponse`\>

#### Type declaration

▸ (`request`): `Promise`<`DidServiceCreateResponse`\>

Creates a DID.

##### Parameters

| Name | Type |
| :------ | :------ |
| `request` | `DidServiceCreateRequest` |

##### Returns

`Promise`<`DidServiceCreateResponse`\>

___

### delete

• `Readonly` **delete**: (`did`: `string`) => `Promise`<`DidServiceDeleteResponse`\>

#### Type declaration

▸ (`did`): `Promise`<`DidServiceDeleteResponse`\>

Deletes a DID where local metadata exists.

##### Parameters

| Name | Type |
| :------ | :------ |
| `did` | `string` |

##### Returns

`Promise`<`DidServiceDeleteResponse`\>

___

### dereference

• `Readonly` **dereference**: <T\>(`didUrl`: `string`) => `Promise`<`DidServiceDereferenceResponse`<`T`\>\>

#### Type declaration

▸ <`T`\>(`didUrl`): `Promise`<`DidServiceDereferenceResponse`<`T`\>\>

Resolves and dereferences DID url.

##### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | extends `object` |

##### Parameters

| Name | Type |
| :------ | :------ |
| `didUrl` | `string` |

##### Returns

`Promise`<`DidServiceDereferenceResponse`<`T`\>\>

___

### info

• `Readonly` **info**: (`did`: `string`) => `Promise`<[`DidServiceInfoResponse`](DidServiceInfoResponse.md)\>

#### Type declaration

▸ (`did`): `Promise`<[`DidServiceInfoResponse`](DidServiceInfoResponse.md)\>

Resolves a DID and combines the result with local metadata if it exists.

##### Parameters

| Name | Type |
| :------ | :------ |
| `did` | `string` |

##### Returns

`Promise`<[`DidServiceInfoResponse`](DidServiceInfoResponse.md)\>

___

### list

• `Readonly` **list**: () => `Promise`<readonly `string`[]\>

#### Type declaration

▸ (): `Promise`<readonly `string`[]\>

Lists all DIDs where local metadata exists.

##### Returns

`Promise`<readonly `string`[]\>
