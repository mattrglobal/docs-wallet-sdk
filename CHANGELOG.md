# Change Log

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
