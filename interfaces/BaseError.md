[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / BaseError

# Interface: BaseError<T\>

Error type used for the Neverthrow error handling pattern.

Example:
```
export enum SignErrorType {
  InvalidPayload = "InvalidPayload",
  ...
}

export type SignError = BaseError & { readonly type: SignErrorType };

const sign = async (): Promise<Result<SignResult, SignError>> => { ... }
```

## Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `string` |

## Table of contents

### Properties

- [cause](BaseError.md#cause)
- [details](BaseError.md#details)
- [message](BaseError.md#message)
- [type](BaseError.md#type)

## Properties

### cause

• `Optional` `Readonly` **cause**: `unknown`

___

### details

• `Optional` `Readonly` **details**: `unknown`

___

### message

• `Optional` `Readonly` **message**: `string`

___

### type

• `Readonly` **type**: `T`
