# Change Log

# 4.0.0

### BREAKING CHANGES

- No longer allow having multiple wallet instance with difference walletIds initialised at the same time. Before
  initialising a wallet instance with a different walletId, the current instance must be closed first.

  ```typescript
  import { initialise } from "@mattrglobal/wallet-sdk-react-native";
  // Previously, the following is allowed.
  const initialiseResult1 = await initialise(walletId1);
  if (initialiseResult1.isErr()) {
    return;
  }
  const wallet1 = initialiseResult1.value;

  const initialiseResult2 = await initialise(walletId2);
  if (initialiseResult2.isErr()) {
    return;
  }
  const wallet2 = initialiseResult2.value;

  // Now, the existing wallet must be closed first
  const initialiseResult1 = await initialise(walletId1);
  if (initialiseResult1.isErr()) {
    return;
  }
  const wallet1 = initialiseResult1.value;
  await wallet1.close();

  const initialiseResult2 = await initialise(walletId2);
  if (initialiseResult2.isErr()) {
    return;
  }
  const wallet2 = initialiseResult2.value;
  ```

- Wallet instance must be closed if it is currently initialised before calling `destroy`, otherwise an exception will be
  thrown.
- Remove error type MalformedEncryptionKeyError that is actually unreacble on `destroy` method

- Realm now requires `>=12.1.0` as peer dependencies to avoid security vulnerability issue in Realm 11.

- refine error types for `wallet.credential.webSemantic.sendPresentationResponse`
  - Removed `SendWebSemanticPresentationResponseErrorType.FailedToSendPresentationResponse` error type
  - Return `SendWebSemanticPresentationResponseErrorType.VerificationFailed` error when presentation response endpoint
    returns 400 Bad Request, which indicates an failure of verifying the presentation response
  - Return `SendWebSemanticPresentationResponseErrorType.VerifierUnavailable` error when presentation response endpoint,
    returns 504 Gateway Timeout, which indicates the verifier is unavailable. The details of the error will contain the
    `verified` for the result of the presentation verification.

### Features

- Add support for mobile credential (ISO Only). This allows user to integrate the mobile credential functionality from
  `@mattrglobal/mobile-credential-react-native` into the wallet sdk. The current functionality includes

  - Retrieving mobile credentials over OpenID4VCI
  - Manage mobile credential store
  - Manage mobile credential trusted issuer certificates
  - Present mobile credentials to a verifier device over bluetooth

- `wallet.did.messaging.openDidCommMessage` now checks JWM message expiries_time when available and return error if the
  message is expired.
- `wallet.credential.webSemantic.sendPresentationResponse` now includes expires_time in the message

### Notes

- Dependencies upgrade and vulnerability fixes

# 3.0.0

### BREAKING CHANGES

- Support partial failure in `wallet.webSemantic.retrieveCredentials` method:

  - `retrieveCredentials` method no longer return error result if it fails to retrieve one of the credentials, instead
    it returns a union of credentials and errors.

    ```typescript
    const retrieveCredentialsResult = await wallet.openid.issuance.retrieveCredentials({
      offer,
      accessToken,
      clientId,
    });

    /**
     * Example `retrieveCredentialsResult`
     * [
     *   {
     *     offer,
     *     credential, // Successfully retrieved verifiable credential
     *   },
     *   {
     *     offer,
     *     error: { type, message, cause }, // Failure
     *   }
     * ]
     */
    ```

- Expose `NetworkError` in case a remote request fails due to a network error or timeout in the following methods:

  - `wallet.credential.webSemantic.verifyCredential` could return type
    `VerifyWebSemanticCredentialErrorType.NetworkError`
  - `wallet.credential.webSemantic.deriveCredential` could return type
    `DeriveWebSemanticCredentialErrorType.NetworkError`
  - `wallet.credential.webSemantic.expandCredential` could return type
    `ExpandWebSemanticCredentialErrorType.NetworkError`
  - `wallet.credential.webSemantic.sendPresentationResponse` could return type
    `SendWebSemanticPresentationResponseErrorType.NetworkError`
  - `wallet.credential.webSemantic.filterCredentialsByQuery` could return type
    `PresentationRequestErrorType.NetworkError`
  - `wallet.openid.issuance.retrieveCredentials` could return type `RetrieveCredentialsErrorType.NetworkError` in the
    new partial error format (see item above)

- Consolidate `create` and `open` into `initialise` method

  ```typescript
  // Previously
  import { create, open } from "@mattrglobal/wallet-sdk-react-native";
  const createWalletResult = await create();
  if (createWalletResult.isErr()) {
    return; // Handle error from createWalletResult.error
  }
  const openWalletResult = await open();
  if (openWalletResult.isErr()) {
    return; // Handle error from openWalletResult.error
  }
  const wallet = openWalletResult.value;
  ...

  // Now
  import { initialise } from "@mattrglobal/wallet-sdk-react-native";
  const initialiseResult = await initialise();
  if (initialiseResult.isErr()) {
    return; // Handle error from initialiseResult.error
  }
  const wallet = initialiseResult.value;
  ...
  ```

### Bug Fixes

- Fix `webSemantic.verifyCredentials` results
  - Do not assume `isRevoked` to be `true` if revocation status check failed
  - Do not assume `expired` to be `false` if credential signature verification failed

### Notes

- Add support for React Native `0.71`

  - Require `realm>=11.10.2`

# 2.1.2

- Add support for `BbsSignature2022` verifiable credentials
- A new peer dependency is required `@mattrglobal/pairing-crypto-rn`

# 2.1.1

- Update change log
- Address cve in semver dependency

# 2.1.0

### Features

- Add support to obtain compact and compact semantic credentials over OpenID4VCI
- Add support to verify compact and compact semantic credentials

### Bug Fixes

- iOS: fix an issue that the keychain got reset after the wallet instance is created.

### Notes

- A new peer dependency is required `@mattrglobal/react-native-cryptography`

# 2.0.0

### BREAKING CHANGES

- Wallet SDK Interface:

  - Rename `wallet.did.create` to `wallet.did.createDid`
  - Rename `wallet.did.delete` to `wallet.did.deleteDid`
  - Rename `wallet.did.list` to `wallet.did.listDids`
  - Rename `wallet.did.resolve` to `wallet.did.resolveDid`
  - Rename `wallet.wellKnownDidConfiguration` to `wallet.did.wellKnownDidConfiguration`
  - Rename `wallet.messaging` to `wallet.did.messaging`
  - Rename `wallet.credential.isSelectivelyDisclosable` to
    `wallet.credential.webSemantic.isCredentialSelectivelyDisclosable`
  - Rename `wallet.credential.derive` to `wallet.credential.webSemantic.deriveCredential`
  - Rename `wallet.credential.verify` to `wallet.credential.webSemantic.verifyCredential`
  - Rename `wallet.credential.expand` to `wallet.credential.webSemantic.expandCredential`
  - Rename `wallet.presentation.create` to `wallet.credential.webSemantic.createPresentation`
  - Rename `wallet.presentation.filterCredentialsByQuery` to `wallet.credential.webSemantic.filterCredentialsByQuery`
  - Rename `wallet.presentation.sendPresentationResponse` to `wallet.credential.webSemantic.sendPresentationResponse`

- Manual Credential Offer:
  - Replace `format` with `profile`

```typescript
const offer: OpenidIssuanceCredentialOffer = {
  ...,
  credentials: [
    {
      scope: "ldp_vc:UniversityDegreeCredential",
      profile: "web-semantic",
      credentialDefinition: {
        "@context": ["https://www.w3.org/2018/credentials/v1"],
        type: ["VerifiableCredential", "UniversityDegreeCredential"],
      },
    }
  ],
};
```

- Retrieve Credentials:
  - Update return type of `wallet.openid.issuance.retrieveCredentials`
    - Replace `format` with `profile`

```typescript
{
  credentials: {
    credential,
    profile,
    did,
  }[];
}
```

### Features

- Add new top-level method `qrcode`

### Bug Fixes

- Replace `big-integer` with `bignumber.js` for the `BigInt` polyfill

# 1.7.1

### Notes

- Internal package maintenance
- Update iOS installation docs

# 1.7.0

### Features

- Add support for resolving DIDCommUri

# 1.6.0

### Features

- Expose document loader timeout value (`httpRequestTimeoutMs`) under `InitOptions` and set the default value to 5
  seconds.

# 1.5.0

### Features

- Add support for dynamic discovery (discover credential offer details via offer URI)

```typescript
/**
 * openid-credential-offer://?credential_offer=encodeURIComponent(JSON.stringify({ credential_issuer, credentials: [{credentialId}], request_parameters? }))
 */
const uri =
  "openid-credential-offer://?credential_offer=%7B%22credential_issuer%22%3A%22https%3A%2F%2Fmyissuer.example.com%22%2C%22credentials%22%3A%5B%22707e920a-f342-443b-ae24-6946b7b5033e%22%5D%2C%22request_parameters%22%3A%7B%22login_hint%22%3A%22ken.huang%40mattr.global%22%2C%22prompt%22%3A%22login%22%7D%7D";

const offer = unwrap(await wallet.openid.issuance.discover(uri));
```

Export types:

- FilterCredentialsByQueryError
- FilterCredentialsByQueryResponse
- PresentationRequestError

Update OpenId issuance offer types (WebSemantic)

```typescript
const offer: OpenidIssuanceCredentialOffer = {
  issuer: "https://example.com/",
  authorizeEndpoint: "https://example.com/oauth/authorize",
  tokenEndpoint: "https://example.com/oauth/token",
  credentialEndpoint: "https://example.com/oauth/credential",
  credentials: [
    {
      format: "ldp_vc",
      scope: "UniversityDegreeCredential",
      credentialDefinition: {
        "@context": ["https://www.w3.org/2018/credentials/v1"],
        type: ["VerifiableCredential", "UniversityDegreeCredential"],
      },
    },
  ],
};
```

### Bug fixes

- Updated `retrieveCredentials` to support deprecated options

# 1.4.1

### Bug Fixes

- Fix React Native android linking

# 1.4.0

### Features

- Expose some internal types and functions
- Export types:
  - SecureKeyValueStoreErrorType
  - assertUnreachable

# 1.3.0

### Features

- Add support for React Native 0.70.0
- Add support for Hermes engine
- Migrate to use `react-native-secure-key-store` 2.0.10

# 1.2.1

### Notes

- Internal package maintenance

# 1.2.0

### Features

- Expose type validation functions:
  - isType
  - assertType
  - OpenidIssuanceCredentialOfferValidator
  - AuthorizeRequestParametersValidator
  - CredentialOfferedValidator
  - OpenidIssuanceGenerateAuthorizeUrlOptionsValidator
  - OpenidIssuanceRetrieveCredentialsOptionsValidator

# 1.1.1

### Notes

- Internal package maintenance

# 1.1.0

### Features

- Add support for obtaining multiple credentials over OpenID4VCI
- Add support for React Native 0.68.5

# 1.0.5

### Notes

- Internal package maintenance

# 1.0.4

### Notes

- Internal package maintenance

# 1.0.3

### Notes

- Internal package maintenance

# 1.0.2

### Notes

- Internal package maintenance

# 1.0.1

### Bug Fixes

- Add missing polyfil and fix build error

### Notes

- Upgrade `@mattrglobal/rn-bbs-signatures` version

# 1.0.0

### Features

- Initialise a wallet
- Manage local DIDs
- Verify issuer DIDs to domain linkage
- Obtain credentials over OIDC Bridge from the issuer
- Verify credentials
- Handle presentation request and present credentials to verifier
- Create and open DID Comm messages
