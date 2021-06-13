[Mattr Wallet SDK React Native](README.md) / Exports

# Mattr Wallet SDK React Native

## Table of contents

### Namespaces

- [Result](modules/result.md)
- [codec](modules/codec.md)

### Enumerations

- [CredentialOfferType](enums/credentialoffertype.md)
- [QueryType](enums/querytype.md)

### Interfaces

- [CheckStatusResult](interfaces/checkstatusresult.md)
- [Credential](interfaces/credential.md)
- [CredentialFrame](interfaces/credentialframe.md)
- [CredentialQueryByExample](interfaces/credentialquerybyexample.md)
- [CredentialQueryByFrame](interfaces/credentialquerybyframe.md)
- [DidAuthQuery](interfaces/didauthquery.md)
- [DidService](interfaces/didservice.md)
- [DidServiceInfoResponse](interfaces/didserviceinforesponse.md)
- [Jwm](interfaces/jwm.md)
- [KeyManagementService](interfaces/keymanagementservice.md)
- [QueryByExample](interfaces/querybyexample.md)
- [QueryByFrame](interfaces/querybyframe.md)
- [VerifiableCredentialProof](interfaces/verifiablecredentialproof.md)
- [VerifiablePresentation](interfaces/verifiablepresentation.md)

### Type aliases

- [BaseSDKError](modules.md#basesdkerror)
- [CloseWalletError](modules.md#closewalleterror)
- [CreateDidError](modules.md#creatediderror)
- [CreateDidResponse](modules.md#createdidresponse)
- [CreatePresentationErrorCouldNotFindSubjectSigningKey](modules.md#createpresentationerrorcouldnotfindsubjectsigningkey)
- [CreatePresentationErrorHolderNotADid](modules.md#createpresentationerrorholdernotadid)
- [CreatePresentationErrorSubjectDidHasNoAuthenticationUrl](modules.md#createpresentationerrorsubjectdidhasnoauthenticationurl)
- [CreatePresentationErrorSubjectNotADid](modules.md#createpresentationerrorsubjectnotadid)
- [CreatePresentationErrors](modules.md#createpresentationerrors)
- [CreatePresentationOptions](modules.md#createpresentationoptions)
- [CredentialData](modules.md#credentialdata)
- [CredentialNotFoundInTokenError](modules.md#credentialnotfoundintokenerror)
- [DecryptError](modules.md#decrypterror)
- [DeleteDidError](modules.md#deletediderror)
- [DeriveError](modules.md#deriveerror)
- [DidDeletionError](modules.md#diddeletionerror)
- [DidNotFoundError](modules.md#didnotfounderror)
- [DidResolutionError](modules.md#didresolutionerror)
- [DiscoverResult](modules.md#discoverresult)
- [EncryptError](modules.md#encrypterror)
- [EncryptOptions](modules.md#encryptoptions)
- [EncryptionKeyNotFoundError](modules.md#encryptionkeynotfounderror)
- [FilterCredentialsByQueryOptions](modules.md#filtercredentialsbyqueryoptions)
- [FilterCredentialsByQueryResponse](modules.md#filtercredentialsbyqueryresponse)
- [GenerateAuthorizeResult](modules.md#generateauthorizeresult)
- [GenerateAuthorizeUrlOptions](modules.md#generateauthorizeurloptions)
- [GenericSdkError](modules.md#genericsdkerror)
- [GetDidsError](modules.md#getdidserror)
- [InvalidBase64URLDecodeError](modules.md#invalidbase64urldecodeerror)
- [InvalidDidError](modules.md#invaliddiderror)
- [InvalidIdTokenError](modules.md#invalididtokenerror)
- [InvalidIssuerUriError](modules.md#invalidissuerurierror)
- [InvalidJSONError](modules.md#invalidjsonerror)
- [InvalidOpenIdConfigurationError](modules.md#invalidopenidconfigurationerror)
- [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror)
- [OidcCredentialOffer](modules.md#oidccredentialoffer)
- [OpenDidCommError](modules.md#opendidcommerror)
- [OpenOptions](modules.md#openoptions)
- [PresentationRequestJwm](modules.md#presentationrequestjwm)
- [Result](modules.md#result)
- [RetrieveCredentialError](modules.md#retrievecredentialerror)
- [RetrieveCredentialOptions](modules.md#retrievecredentialoptions)
- [RetrieveCredentialResult](modules.md#retrievecredentialresult)
- [SendPresentationErrorMissingSender](modules.md#sendpresentationerrormissingsender)
- [SendPresentationResponseOptions](modules.md#sendpresentationresponseoptions)
- [SignError](modules.md#signerror)
- [VerifiableCredential](modules.md#verifiablecredential)
- [VerifiablePresentationRequestQuery](modules.md#verifiablepresentationrequestquery)
- [VerifyCredentialError](modules.md#verifycredentialerror)
- [VerifyCredentialOptions](modules.md#verifycredentialoptions)
- [VerifyCredentialResult](modules.md#verifycredentialresult)
- [VerifyCredentialStatus](modules.md#verifycredentialstatus)
- [VerifyError](modules.md#verifyerror)
- [Wallet](modules.md#wallet)
- [WalletAlreadyCreatedError](modules.md#walletalreadycreatederror)

### Functions

- [create](modules.md#create)
- [open](modules.md#open)
- [unwrap](modules.md#unwrap)

## Type aliases

### BaseSDKError

Ƭ **BaseSDKError**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `cause?` | `Error` \| `unknown` |
| `message` | `string` |
| `type` | `string` |

___

### CloseWalletError

Ƭ **CloseWalletError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CloseWalletError"``  }

___

### CreateDidError

Ƭ **CreateDidError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CreateDidError"``  }

___

### CreateDidResponse

Ƭ **CreateDidResponse**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `did` | `string` | The new DID that has been created |

___

### CreatePresentationErrorCouldNotFindSubjectSigningKey

Ƭ **CreatePresentationErrorCouldNotFindSubjectSigningKey**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CreatePresentationErrorCouldNotFindSubjectSigningKey"``  }

___

### CreatePresentationErrorHolderNotADid

Ƭ **CreatePresentationErrorHolderNotADid**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CreatePresentationErrorHolderNotADid"``  }

___

### CreatePresentationErrorSubjectDidHasNoAuthenticationUrl

Ƭ **CreatePresentationErrorSubjectDidHasNoAuthenticationUrl**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CreatePresentationErrorSubjectDidHasNoAuthenticationUrl"``  }

___

### CreatePresentationErrorSubjectNotADid

Ƭ **CreatePresentationErrorSubjectNotADid**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CreatePresentationErrorSubjectNotADid"``  }

___

### CreatePresentationErrors

Ƭ **CreatePresentationErrors**: [CreatePresentationErrorSubjectNotADid](modules.md#createpresentationerrorsubjectnotadid) \| [CreatePresentationErrorHolderNotADid](modules.md#createpresentationerrorholdernotadid) \| [CreatePresentationErrorSubjectDidHasNoAuthenticationUrl](modules.md#createpresentationerrorsubjectdidhasnoauthenticationurl) \| [CreatePresentationErrorCouldNotFindSubjectSigningKey](modules.md#createpresentationerrorcouldnotfindsubjectsigningkey)

___

### CreatePresentationOptions

Ƭ **CreatePresentationOptions**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `challenge` | `string` |
| `credentials?` | readonly [VerifiableCredential](modules.md#verifiablecredential)[] |
| `domain` | `string` |
| `holder?` | `string` |

___

### CredentialData

Ƭ **CredentialData**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `credential` | [Credential](interfaces/credential.md) |

___

### CredentialNotFoundInTokenError

Ƭ **CredentialNotFoundInTokenError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"CredentialNotFoundInTokenError"``  }

___

### DecryptError

Ƭ **DecryptError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"DecryptError"``  }

___

### DeleteDidError

Ƭ **DeleteDidError**: [DidNotFoundError](modules.md#didnotfounderror) \| [DidDeletionError](modules.md#diddeletionerror)

___

### DeriveError

Ƭ **DeriveError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"DeriveError"``  }

___

### DidDeletionError

Ƭ **DidDeletionError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"DidDeletionError"``  }

___

### DidNotFoundError

Ƭ **DidNotFoundError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"DidNotFoundError"``  }

___

### DidResolutionError

Ƭ **DidResolutionError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"DidResolutionError"``  }

___

### DiscoverResult

Ƭ **DiscoverResult**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `offer` | [OidcCredentialOffer](modules.md#oidccredentialoffer) | An OIDC credential offer |

___

### EncryptError

Ƭ **EncryptError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"EncryptError"``  }

___

### EncryptOptions

Ƭ **EncryptOptions**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `payload` | `string` \| `Record`<string, unknown\> | The payload to encrypt |
| `recipientDids` | readonly `string`[] | The DIDs of the message recipients |
| `senderDid` | `string` | The DID of the sender |

___

### EncryptionKeyNotFoundError

Ƭ **EncryptionKeyNotFoundError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"EncryptionKeyNotFoundError"``  }

___

### FilterCredentialsByQueryOptions

Ƭ **FilterCredentialsByQueryOptions**<T\>: `Object`

Filter credentials by query options

#### Type parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `T` | `T`: [CredentialData](modules.md#credentialdata) | Additional data extending [CredentialData](modules.md#credentialdata) |

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `credentials` | readonly `T`[] | A list of credential data to query against |
| `query` | [VerifiablePresentationRequestQuery](modules.md#verifiablepresentationrequestquery) | A [VerifiablePresentationRequestQuery](modules.md#verifiablepresentationrequestquery) to filter the credentials with |

___

### FilterCredentialsByQueryResponse

Ƭ **FilterCredentialsByQueryResponse**<T\>: `Object`

Filter credentials by query response

#### Type parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `T` | `T`: [CredentialData](modules.md#credentialdata) | Additional data extending [CredentialData](modules.md#credentialdata) |

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | `ReadonlyArray`<`Object`\> | An array of credentials matching each query |
| `type` | [QueryType](enums/querytype.md) | The query type used for filtering |

___

### GenerateAuthorizeResult

Ƭ **GenerateAuthorizeResult**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `codeVerifier` | `string` |
| `nonce` | `string` |
| `url` | `string` |

___

### GenerateAuthorizeUrlOptions

Ƭ **GenerateAuthorizeUrlOptions**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `clientId?` | `string` |
| `did` | `string` |
| `offer` | [OidcCredentialOffer](modules.md#oidccredentialoffer) |
| `redirectUri?` | `string` |
| `state?` | `string` |

___

### GenericSdkError

Ƭ **GenericSdkError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"GenericError"``  }

___

### GetDidsError

Ƭ **GetDidsError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"GetDidsError"``  }

___

### InvalidBase64URLDecodeError

Ƭ **InvalidBase64URLDecodeError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidBase64URLDecodeError"``  }

___

### InvalidDidError

Ƭ **InvalidDidError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidDidError"``  }

___

### InvalidIdTokenError

Ƭ **InvalidIdTokenError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidIdTokenError"``  }

___

### InvalidIssuerUriError

Ƭ **InvalidIssuerUriError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidIssuerUriError"``  }

___

### InvalidJSONError

Ƭ **InvalidJSONError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidJSONError"``  }

___

### InvalidOpenIdConfigurationError

Ƭ **InvalidOpenIdConfigurationError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"InvalidOpenIdConfigurationError"``  }

___

### MalformedEncryptionKeyError

Ƭ **MalformedEncryptionKeyError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"MalformedEncryptionKeyError"``  }

___

### OidcCredentialOffer

Ƭ **OidcCredentialOffer**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `authorizeEndpoint` | `string` |
| `claims` | readonly `string`[] |
| `issuer` | `string` |
| `name` | `string` |
| `tokenEndpoint` | `string` |
| `type` | [CredentialOfferType](enums/credentialoffertype.md) |

___

### OpenDidCommError

Ƭ **OpenDidCommError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"OpenDidCommError"``  }

___

### OpenOptions

Ƭ **OpenOptions**: `Object`

Options to configure when opening an existing wallet

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `httpResolverUrl?` | `string` | Specifies the URL the http resolver will use  **`defaultvalue`** https://uniresolver-api.mattr.global |

___

### PresentationRequestJwm

Ƭ **PresentationRequestJwm**: [Jwm](interfaces/jwm.md) & { `body`: `VerifiablePresentationRequest` ; `from`: `string` ; `reply_to`: readonly `string`[] ; `reply_url`: `string` ; `type`: `PresentationRequestType`  }

___

### Result

Ƭ **Result**<T, E\>: `Ok`<T, E\> \| `Err`<T, E\>

#### Type parameters

| Name |
| :------ |
| `T` |
| `E` |

___

### RetrieveCredentialError

Ƭ **RetrieveCredentialError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"RetrieveCredentialError"``  }

___

### RetrieveCredentialOptions

Ƭ **RetrieveCredentialOptions**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `clientId?` | `string` |
| `code` | `string` |
| `codeVerifier` | `string` |
| `nonce` | `string` |
| `offer` | [OidcCredentialOffer](modules.md#oidccredentialoffer) |
| `redirectUri` | `string` |

___

### RetrieveCredentialResult

Ƭ **RetrieveCredentialResult**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `credential` | [VerifiableCredential](modules.md#verifiablecredential) | The retrieved credential |

___

### SendPresentationErrorMissingSender

Ƭ **SendPresentationErrorMissingSender**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"SendPresentationErrorMissingSender"``  }

___

### SendPresentationResponseOptions

Ƭ **SendPresentationResponseOptions**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `presentation` | [VerifiablePresentation](interfaces/verifiablepresentation.md) |
| `presentationRequest` | [PresentationRequestJwm](modules.md#presentationrequestjwm) |
| `senderDid?` | `string` |

___

### SignError

Ƭ **SignError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"SignError"``  }

___

### VerifiableCredential

Ƭ **VerifiableCredential**: [Credential](interfaces/credential.md) & { `id?`: `string` ; `proof`: [VerifiableCredentialProof](interfaces/verifiablecredentialproof.md) \| readonly [VerifiableCredentialProof](interfaces/verifiablecredentialproof.md)[]  }

___

### VerifiablePresentationRequestQuery

Ƭ **VerifiablePresentationRequestQuery**: [DidAuthQuery](interfaces/didauthquery.md) \| [QueryByExample](interfaces/querybyexample.md) \| [QueryByFrame](interfaces/querybyframe.md)

___

### VerifyCredentialError

Ƭ **VerifyCredentialError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"VerifyCredentialError"``  }

___

### VerifyCredentialOptions

Ƭ **VerifyCredentialOptions**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `credential` | [VerifiableCredential](modules.md#verifiablecredential) | The credential to verify |

___

### VerifyCredentialResult

Ƭ **VerifyCredentialResult**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `credentialVerified` | `boolean` |
| `status?` | [VerifyCredentialStatus](modules.md#verifycredentialstatus) |

___

### VerifyCredentialStatus

Ƭ **VerifyCredentialStatus**: [CheckStatusResult](interfaces/checkstatusresult.md) \| `undefined`

___

### VerifyError

Ƭ **VerifyError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"VerifyError"``  }

___

### Wallet

Ƭ **Wallet**: `Object`

An instance of a wallet

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `close` | () => `Promise`<[Result](modules/result.md)<void, [CloseWalletError](modules.md#closewalleterror)\>\> | Closes the wallet  **`remarks`** Wallet instance will not function anymore after close   **`returns`** A promise that resolves to a [Result](modules/result.md) containing void on ok or a [CloseWalletError](modules.md#closewalleterror) on error |
| `credential` | `Object` | Namespace for credential operations |
| `credential.derive` | (`credential`: [VerifiableCredential](modules.md#verifiablecredential), `queryFrame`: [CredentialFrame](interfaces/credentialframe.md)) => `Promise`<[Result](modules/result.md)<[VerifiableCredential](modules.md#verifiablecredential), [DeriveError](modules.md#deriveerror)\>\> | Derives a credential based on a frame  **`param`** The full credential we want to create the derived credential from  **`param`** The [CredentialFrame](interfaces/credentialframe.md) used to derive the credential  **`returns`** A promise that resolves to a [Result](modules/result.md) containing the derived [VerifiableCredential](modules.md#verifiablecredential) on ok or a [DeriveError](modules.md#deriveerror) on error |
| `credential.filterCredentialsByQuery` | <T\>(`options`: [FilterCredentialsByQueryOptions](modules.md#filtercredentialsbyqueryoptions)<T\>) => [FilterCredentialsByQueryResponse](modules.md#filtercredentialsbyqueryresponse)<T\> | Filters a list of credentials based on a query  **`param`** [FilterCredentialsByQueryOptions](modules.md#filtercredentialsbyqueryoptions) containing the credentials and filter  **`returns`** [FilterCredentialsByQueryResponse](modules.md#filtercredentialsbyqueryresponse) containing the credentials that match the filter |
| `credential.isSelectivelyDisclosable` | (`credential`: [VerifiableCredential](modules.md#verifiablecredential)) => `boolean` | Determines if a credential is capable of selective disclosure  **`param`** The credential to check  **`returns`** A boolean representing if the credential is capable of selective disclosure |
| `credential.verify` | (`options`: [VerifyCredentialOptions](modules.md#verifycredentialoptions)) => `Promise`<[Result](modules/result.md)<[VerifyCredentialResult](modules.md#verifycredentialresult), [VerifyCredentialError](modules.md#verifycredentialerror)\>\> | Attempts to verify a credential  **`param`** [VerifyCredentialOptions](modules.md#verifycredentialoptions) containing a credential to verify |
| `did` | `Object` | Namespace for DID operations |
| `did.create` | () => `Promise`<[Result](modules/result.md)<[CreateDidResponse](modules.md#createdidresponse), [CreateDidError](modules.md#creatediderror)\>\> | Create a new DID in the wallet  **`returns`** A promise that resolves to a [Result](modules/result.md) containing [CreateDidResponse](modules.md#createdidresponse) on ok or a [CreateDidError](modules.md#creatediderror) on error |
| `did.delete` | (`did`: `string`) => `Promise`<[Result](modules/result.md)<void, [DeleteDidError](modules.md#deletediderror)\>\> | Delete an existing DID in the wallet  **`param`** The DID to delete from the wallet  **`returns`** A promise that resolves to void on ok or a [DeleteDidError](modules.md#deletediderror) on error |
| `did.list` | () => `Promise`<[Result](modules/result.md)<readonly `string`[], [GetDidsError](modules.md#getdidserror)\>\> | List all DIDs created within the wallet  **`returns`** A promise that resolves to a [Result](modules/result.md) containing a list of DIDs on ok or a  [GetDidsError](modules.md#getdidserror) on error |
| `did.resolve` | (`did`: `string`) => `Promise`<[Result](modules/result.md)<[DidServiceInfoResponse](interfaces/didserviceinforesponse.md), [DidResolutionError](modules.md#didresolutionerror)\>\> | Resolves any DID into a DID document and the local metadata  **`param`** The DID to resolve  **`returns`** Resolves to a [Result](modules/result.md) containing a list of DIDs on ok or a  [GetDidsError](modules.md#getdidserror) on error |
| `didService` | [DidService](interfaces/didservice.md) | An exposed [DidService](interfaces/didservice.md)  **`privateremarks`** Direct exposure of DidService will be removed in the future |
| `isOpen` | () => `boolean` | Indicates if the wallet is open |
| `kms` | [KeyManagementService](interfaces/keymanagementservice.md) | An exposed [KeyManagementService](interfaces/keymanagementservice.md)  **`privateremarks`** Direct exposure of KeyManagementService will be removed in the future |
| `messaging` | `Object` | Namespace for messaging operations |
| `messaging.encrypt` | (`options`: [EncryptOptions](modules.md#encryptoptions)) => `Promise`<[Result](modules/result.md)<JweJsonSerialization, [EncryptError](modules.md#encrypterror)\>\> | Encrypts a message  **`param`** [EncryptOptions](modules.md#encryptoptions) for encrypting the message  **`returns`** A promise that resolves to a [Result](modules/result.md) containing {@link JweJsonSerialization} on ok or [EncryptError](modules.md#encrypterror) on error |
| `messaging.openDidCommMessage` | (`message`: `unknown`) => `Promise`<[Result](modules/result.md)<[Jwm](interfaces/jwm.md), [OpenDidCommError](modules.md#opendidcommerror) \| [VerifyError](modules.md#verifyerror) \| [DecryptError](modules.md#decrypterror)\>\> | Opens a DIDComm message  **`param`** The message to open  **`returns`** A promise that resolves to a [Result](modules/result.md) containing [Jwm](interfaces/jwm.md) on ok or a [OpenDidCommError](modules.md#opendidcommerror), [VerifyError](modules.md#verifyerror) or a [DecryptError](modules.md#decrypterror) on error |
| `messaging.sign` | (`payload`: `string` \| `Record`<string, unknown\>, `senderDid`: `string`) => `Promise`<[Result](modules/result.md)<string, [SignError](modules.md#signerror)\>\> | Signs a message  **`param`** The message payload to sign  **`param`** The DID of the sender used for signing  **`returns`** A promise that resolves to a [Result](modules/result.md) containing [Jwm](interfaces/jwm.md) on ok or a [OpenDidCommError](modules.md#opendidcommerror), [VerifyError](modules.md#verifyerror) or a [DecryptError](modules.md#decrypterror) on error |
| `oidc` | `Object` | Namespace for OIDC operations |
| `oidc.discover` | (`issuerUri`: `string`) => `Promise`<[Result](modules/result.md)<[DiscoverResult](modules.md#discoverresult), [InvalidIssuerUriError](modules.md#invalidissuerurierror) \| [InvalidOpenIdConfigurationError](modules.md#invalidopenidconfigurationerror)\>\> | Discover credential offer from OIDC's wellknown configuration endpoint  **`param`** The URI of the OIDC credential issuer example: openid://discovery?issuer=https://government-of-aotearoa.platform.mattr.global  **`returns`** - Resolves to a [Result](modules/result.md) containing the [DiscoverResult](modules.md#discoverresult) on ok or a [InvalidIssuerUriError](modules.md#invalidissuerurierror) or [InvalidOpenIdConfigurationError](modules.md#invalidopenidconfigurationerror) on error |
| `oidc.generateAuthorizeUrl` | (`options`: [GenerateAuthorizeUrlOptions](modules.md#generateauthorizeurloptions)) => `Promise`<[Result](modules/result.md)<[GenerateAuthorizeResult](modules.md#generateauthorizeresult), [InvalidDidError](modules.md#invaliddiderror) \| [SignError](modules.md#signerror)\>\> | Generates an authorization URL  **`param`** [GenerateAuthorizeUrlOptions](modules.md#generateauthorizeurloptions)  **`returns`** A promise that resolves to a [Result](modules/result.md) containing the [GenerateAuthorizeResult](modules.md#generateauthorizeresult) on ok or a [InvalidDidError](modules.md#invaliddiderror) or [SignError](modules.md#signerror) on error |
| `oidc.retrieveCredential` | (`options`: [RetrieveCredentialOptions](modules.md#retrievecredentialoptions)) => `Promise`<[Result](modules/result.md)<[RetrieveCredentialResult](modules.md#retrievecredentialresult), [RetrieveCredentialError](modules.md#retrievecredentialerror) \| [InvalidIdTokenError](modules.md#invalididtokenerror) \| [CredentialNotFoundInTokenError](modules.md#credentialnotfoundintokenerror)\>\> | Retrieves a credential from the OIDC provider  **`param`** [RetrieveCredentialOptions](modules.md#retrievecredentialoptions)  **`returns`** A promise that resolves to a [Result](modules/result.md) containing a [RetrieveCredentialResult](modules.md#retrievecredentialresult) on ok or a [RetrieveCredentialError](modules.md#retrievecredentialerror), [InvalidIdTokenError](modules.md#invalididtokenerror) or [CredentialNotFoundInTokenError](modules.md#credentialnotfoundintokenerror) on error |
| `presentation` | `Object` | Namespace for presentation operations |
| `presentation.create` | (`options`: [CreatePresentationOptions](modules.md#createpresentationoptions)) => `Promise`<[Result](modules/result.md)<[VerifiablePresentation](interfaces/verifiablepresentation.md), [CreatePresentationErrors](modules.md#createpresentationerrors)\>\> | Create a verifiable presentation  **`param`** [CreatePresentationOptions](modules.md#createpresentationoptions)  **`returns`** A promise that resolves to a [Result](modules/result.md) containing a [VerifiablePresentation](interfaces/verifiablepresentation.md) on ok or a [CreatePresentationErrors](modules.md#createpresentationerrors) on error |
| `presentation.sendPresentationResponse` | (`options`: [SendPresentationResponseOptions](modules.md#sendpresentationresponseoptions)) => `Promise`<[Result](modules/result.md)<void, HttpError \| [EncryptError](modules.md#encrypterror) \| [SendPresentationErrorMissingSender](modules.md#sendpresentationerrormissingsender)\>\> | Sends a presentation response  **`param`** [SendPresentationResponseOptions](modules.md#sendpresentationresponseoptions)  **`returns`** A promise that resolves to a [Result](modules/result.md) containing void on ok or a {@link HttpError}, [EncryptError](modules.md#encrypterror) or an [SendPresentationErrorMissingSender](modules.md#sendpresentationerrormissingsender) on error |
| `wellKnownDidConfiguration` | `Object` | Namespace for wellknown configuration operations |
| `wellKnownDidConfiguration.validate` | (`domain`: `string`, `did`: `string`) => `Promise`<boolean\> | Validates a DID belongs to domain  **`param`** The domain to check has authority of a DID  **`param`** The DID to check belongs to a domain  **`returns`** A boolean representing if the DID belongs to a domain |

___

### WalletAlreadyCreatedError

Ƭ **WalletAlreadyCreatedError**: [BaseSDKError](modules.md#basesdkerror) & { `type`: ``"WalletAlreadyCreatedError"``  }

## Functions

### create

▸ `Const` **create**(): `Promise`<[Result](modules/result.md)<void, [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) \| [WalletAlreadyCreatedError](modules.md#walletalreadycreatederror)\>\>

Generates new encryption keys and storage directories required for a wallet

**`remarks`**
This function must be called before trying to open the wallet

#### Returns

`Promise`<[Result](modules/result.md)<void, [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) \| [WalletAlreadyCreatedError](modules.md#walletalreadycreatederror)\>\>

A [Result](modules/result.md) containing void on ok and either a [WalletAlreadyCreatedError](modules.md#walletalreadycreatederror) or [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) on error

___

### open

▸ `Const` **open**(`options`): `Promise`<[Result](modules/result.md)<[Wallet](modules.md#wallet), [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) \| [EncryptionKeyNotFoundError](modules.md#encryptionkeynotfounderror)\>\>

Open an existing wallet with stored encryption keys

**`remarks`**
The wallet must have been created before trying to call open so the storage directories and encryption keys exist

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [OpenOptions](modules.md#openoptions) | [OpenOptions](modules.md#openoptions) containing the options for the open function |

#### Returns

`Promise`<[Result](modules/result.md)<[Wallet](modules.md#wallet), [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) \| [EncryptionKeyNotFoundError](modules.md#encryptionkeynotfounderror)\>\>

A [Result](modules/result.md) containing the open [Wallet](modules.md#wallet) object on ok or a [MalformedEncryptionKeyError](modules.md#malformedencryptionkeyerror) or [EncryptionKeyNotFoundError](modules.md#encryptionkeynotfounderror) on error

___

### unwrap

▸ `Const` **unwrap**<T\>(`result`): `T`

A utility function to get the value from a [Result](modules/result.md) or throw if there was an error

**`remarks`**
Allows you to get the value of a result directly or handle an error [Result](modules/result.md) as an exception

#### Type parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `T` | `T` = `unknown` | the expected value of an ok result |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | [Result](modules/result.md)<T, unknown\> | The [Result](modules/result.md) to unwrap |

#### Returns

`T`
