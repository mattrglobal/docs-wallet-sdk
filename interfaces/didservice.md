[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / DidService

# Interface: DidService

## Table of contents

### Properties

- [create](didservice.md#create)
- [delete](didservice.md#delete)
- [dereference](didservice.md#dereference)
- [info](didservice.md#info)
- [list](didservice.md#list)

## Properties

### create

• `Readonly` **create**: (`request`: `DidServiceCreateRequest`) => `Promise`<DidServiceCreateResponse\>

Creates a DID.

#### Type declaration

▸ (`request`): `Promise`<DidServiceCreateResponse\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `request` | `DidServiceCreateRequest` |

##### Returns

`Promise`<DidServiceCreateResponse\>

___

### delete

• `Readonly` **delete**: (`did`: `string`) => `Promise`<DidServiceDeleteResponse\>

Deletes a DID where local metadata exists.

#### Type declaration

▸ (`did`): `Promise`<DidServiceDeleteResponse\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `did` | `string` |

##### Returns

`Promise`<DidServiceDeleteResponse\>

___

### dereference

• `Readonly` **dereference**: <T\>(`didUrl`: `string`) => `Promise`<DidServiceDereferenceResponse<T\>\>

Resolves and dereferences DID url.

#### Type declaration

▸ <T\>(`didUrl`): `Promise`<DidServiceDereferenceResponse<T\>\>

##### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `T`: `object` |

##### Parameters

| Name | Type |
| :------ | :------ |
| `didUrl` | `string` |

##### Returns

`Promise`<DidServiceDereferenceResponse<T\>\>

___

### info

• `Readonly` **info**: (`did`: `string`) => `Promise`<[DidServiceInfoResponse](didserviceinforesponse.md)\>

Resolves a DID and combines the result with local metadata if it exists.

#### Type declaration

▸ (`did`): `Promise`<[DidServiceInfoResponse](didserviceinforesponse.md)\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `did` | `string` |

##### Returns

`Promise`<[DidServiceInfoResponse](didserviceinforesponse.md)\>

___

### list

• `Readonly` **list**: () => `Promise`<readonly `string`[]\>

Lists all DIDs where local metadata exists.

#### Type declaration

▸ (): `Promise`<readonly `string`[]\>

##### Returns

`Promise`<readonly `string`[]\>
