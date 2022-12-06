[Mattr Wallet SDK React Native](../README.md) / [Exports](../modules.md) / Result

# Namespace: Result

## Table of contents

### Functions

- [fromThrowable](result.md#fromthrowable)

## Functions

### fromThrowable

▸ **fromThrowable**<Fn, E\>(`fn`, `errorFn?`): (...`args`: `Parameters`<Fn\>) => [Result](result.md)<ReturnType<Fn\>, E\>

Wraps a function with a try catch, creating a new function with the same
arguments but returning `Ok` if successful, `Err` if the function throws

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Fn` | `Fn`: (...`args`: readonly `any`[]) => `any` |
| `E` | `E` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `fn` | `Fn` | function to wrap with ok on success or err on failure |
| `errorFn?` | (`e`: `unknown`) => `E` | when an error is thrown, this will wrap the error result if provided |

#### Returns

`fn`

▸ (...`args`): [Result](result.md)<ReturnType<Fn\>, E\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `...args` | `Parameters`<Fn\> |

##### Returns

[Result](result.md)<ReturnType<Fn\>, E\>
