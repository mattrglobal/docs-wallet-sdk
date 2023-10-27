MATTR Wallet SDK React Native / [Exports](modules.md)

# wallet-sdk-react-native

# Table of Contents

- [Features](#features)
- [Getting started](#getting-started)
- [Usage](#usage)
  - [Wallet](#wallet)
  - [Retrieving credentials via OpenID4VCI ](#retrieving-credentials-via-openid4vci)
  - [Retrieving credentials via OIDC Bridge](#retrieving-credentials-via-oidc-bridge)
  - [DIDComm message](#didcomm-message)
  - [Web Semantic Credential](#web-semantic-credential)
  - [Compact Credential](#compact-credential)
  - [Compact Semantic Credential](#compact-semantic-credential)
  - [Mobile Credential](#mobile-credential)
  - [Error handling](#error-handling)

# Features

- Manage local DIDs
- DIDComm messsaging
- Validate a DID to domain linkage
- Retrieve credentials over OpenID4VCI
- Retrieve credentials over OIDC Bridge
- Verify and present web semantic credentials
- Verify compact credentials
- Verify compact semantic credentials
- Hold, verify and present mobile credentials

# High level overview

![High Level](./docs/highlevel.drawio.png)

# Getting started

## How to get access to MATTR Pi Wallet SDK

To gain access to the MATTR Pi Wallet SDK, please follow these steps:

1. Request or download the ["Terms of Agreement"](https://learn.mattr.global/docs/terms/mattr-pi-sdk-licence-agreement).
2. Read the "Terms of Agreement", sign it, and return it to us.
3. Create an account at [NPMJS - Node package manager for JavaScript](https://www.npmjs.com).
4. Ensure multi-factor authentication (MFA) is configured on NPMJS Account.
5. Create a personal access token
   [Create a personal access token](https://docs.npmjs.com/creating-and-viewing-access-tokens).
6. Supply the NPMJS (Node package manager for JavaScript) account name back to MATTR.
7. MATTR will process the request and provision access to the MATTR Pi Wallet SDK if approved.

> Please reach out to us in case you need any assistance [Get in touch](https://mattr.global/contact).

## Install dependencies

Add this SDK as a dependency to the react native app:

```
yarn add @mattrglobal/wallet-sdk-react-native
```

The SDK relies on a set of peer dependencies that contain native libraries and iOS pods. With React Native >=0.60 these
dependencies will be autolinked.

Install the peer dependencies:

```
yarn add react-native-securerandom@1.0.1 realm@12.2.1 react-native-fs@2.20.0 react-native-secure-key-store@2.0.10 @mattrglobal/rn-bbs-signatures@1.0.0 react-native-get-random-values@1.7.0 @mattrglobal/react-native-cryptography@1.1.0 @mattrglobal/pairing-crypto-rn@0.4.1

Note: we tested with react-native 0.71.12
```

**React Native <0.60**

Please see the specific instructions for each dependency regarding linking prior to React Native 0.60.

## Android only

Make sure the following repository is included under `android/build.gradle` `allprojects.repositories`:

```
allprojects {
    repositories {
        ...
        maven { url 'https://oss.sonatype.org/content/repositories/snapshots/' }
        ...
    }
}
```

## iOS only

Add the pod for bbs-signatures to the podfile in `ios/Podfile`:

```
  pod 'bbs-signatures', :git => 'https://github.com/mattrglobal/ffi-bbs-signatures'
```

Run pod install:

```
cd ios && pod install
```

Add `arm64` to all profiles under: xcode -> Build Settings -> Excluded Architectures -> Any iOS Simulator SDK, it should
show the following changes under `xxx.xcodeproj` for each of the profiles

```
"EXCLUDED_ARCHS[sdk=iphonesimulator*]" = arm64;
```

If your app was initially created with `react-native@0.61.*` or older you may need to change update your
`ios/*.xcodeproj` configuration.

Any reference of the `DEAD_CODE_STRIPPING` flag must be removed or set to `YES`, this is required to maintain
compatibility for the newer & older versions of `react-native`.

```diff
- DEAD_CODE_STRIPPING = NO;
```

# Usage

## Wallet

Initialise a wallet instance

```typescript
import { initialise } from "@mattrglobal/wallet-sdk-react-native";

const initialiseWalletResult = await initialise();

if (initialiseWalletResult.isErr()) {
  // Handle error from initialiseWalletResult.error
  return;
}

const wallet = initialiseWalletResult.value;
```

It's possible to maintain multiple isolated wallet instances too. This can be achieved by using a different walletId
during initialisation. Note that in this case, you must close the current wallet instance before initialising a new one
with a different walletId.

```typescript
import { initialise } from "@mattrglobal/wallet-sdk-react-native";

// to use wallet1
const initialiseWallet1Result = await initialise({ walletId: "id1" });

if (initialiseWallet1Result.isErr()) {
  // Handle error from initialiseWalletResult.error
  return;
}
const wallet1 = initialiseWallet1Result.value;

// to use wallet2
await wallet1.close();
const initialiseWallet2Result = await initialise({ walletId: "id2" });
const wallet2 = initialiseWallet1Result.value;
```

Destroy the wallet

> Note: you must close the wallet instance that is currently initialised before calling `destroy`, otherwise an
> exception will be thrown.

```typescript
import { destroy } from "@mattrglobal/wallet-sdk-react-native";

await destroy({ walletId });
```

## Retrieving credentials via OpenID4VCI

Discover credential offer details via offer URI

```typescript
/***
 * openid-credential-offer://?credential_offer=encodeURIComponent(JSON.stringify({ credential_issuer, credentials: [{credentialId}], request_parameters? }))
 */
const uri =
  "openid-credential-offer://?credential_offer=%7B%22credential_issuer%22%3A%22https%3A%2F%2Fmyissuer.example.com%22%2C%22credentials%22%3A%5B%22707e920a-f342-443b-ae24-6946b7b5033e%22%5D%2C%22request_parameters%22%3A%7B%22login_hint%22%3A%22user%40example.com%22%2C%22prompt%22%3A%22login%22%7D%7D";

const discoveryResult = await wallet.openid.issuance.discover(uri);
if (discoveryResult.isErr()) {
  // Handle error from discoveryResult.error
}
const { offer } = discoveryResult.value;
```

Or construct offer manually

```typescript
const offer: OpenidIssuanceCredentialOffer = {
  issuer: "https://example.com/",
  authorizeEndpoint: "https://example.com/oauth/authorize",
  tokenEndpoint: "https://example.com/oauth/token",
  credentialEndpoint: "https://example.com/oauth/credential",
  credentials: [
    {
      profile: "web-semantic",
      scope: "ldp_vc:UniversityDegreeCredential",
      credentialDefinition: {
        "@context": ["https://www.w3.org/2018/credentials/v1"],
        type: ["VerifiableCredential", "UniversityDegreeCredential"],
      },
    },
  ],
};
```

Configure OAuth client id and redirect uri

```typescript
const clientId = "myAppClientId";
const redirectUri = "myapp://credentials/callback";
```

Generate an authorization url and open in a web browser

```typescript
import { Linking } from "react-native";

const generateAuthorizeUrlResult = await wallet.openid.issuance.generateAuthorizeUrl({ offer, clientId, redirectUri });

if (generateAuthorizeUrlResult.isErr()) {
  // Handle error from generateAuthorizeUrlResult.error
  return;
}

const { url, codeVerifier } = generateAuthorizeUrlResult.value;
await Linking.openURL(url);
```

Handle authorization success callback

```typescript
myapp://credentials/callback?code=...&iss=...
```

Retrieve token

```typescript
const retrieveTokenResult = await wallet.openid.issuance.retrieveToken({
  offer,
  clientId,
  redirectUri,
  codeVerifier,
  code: route.params.code, // code comes authorization success callback above
});

if (retrieveTokenResult.isErr()) {
  // Handle error from retrieveTokenResult.error
  return;
}

const { accessToken } = retrieveTokenResult.value;
```

Retrieve credentials

```typescript
const retrieveCredentialsResult = await wallet.openid.issuance.retrieveCredentials({
  offer,
  accessToken,
  clientId,
});

retrieveCredentialsResult.forEach((credentialOfferResult) => {
  if ("error" in credentialOfferResult) {
    const { offer, error } = credentialOfferResult;

    // Handle error from retrieveCredentialsResult.error
  } else {
    const { offer, result } = credentialOfferResult;
  }
});
```

## Retrieving credentials via OIDC Bridge

Discover OIDC credential offer

```typescript
const discoverResult = await wallet.oidc.discover("openid://discovery?issuer=https://issuer.example.com");

if (discoverResult.isErr()) {
  // Handle error from discoverResult.error
  return;
}

const { offer } = discoverResult.value;
```

Create a local subject DID for the credential

```typescript
const createDidResult = await wallet.did.createDid();

if (createDidResult.isErr()) {
  // Handle error from createDidResult.error
  return;
}

const { did } = createDidResult.value;
```

Generate an OpenID authorization url to request the credential

```typescript
import { Linking } from "react-native";

const genUrlResult = await wallet.oidc.generateAuthorizeUrl({ offer, did });

if (genUrlResult.isErr()) {
  // Handle error from genUrlResult.error
  return;
}

const { url, codeVerifier, nonce } = genUrlResult.value;
await Linking.openURL(url);
```

Retrieve the credential on authorization success callback

```typescript
const retrieveResult = (retrieveCredential = await wallet.oidc.retrieveCredential({
  offer,
  codeVerifier,
  nonce,
  code: route.params.code, // code comes from part of the callback url
}));

if (retrieveResult.isErr()) {
  // Handle error from retrieveResult.error
  return;
}

const { credential } = retrieveResult.value;
```

## DIDComm message

Resolve a didcomm message from a didcomm URI

```typescript
const resolveDidCommUriResult = await wallet.did.messaging.resolveDidCommUri(uri);
if (resolveDidCommUriResult.isErr()) {
  // Handle error from resolveDidCommUriResult.error
  return;
}
const message = resolveDidCommUriResult.value;
```

Open a didcomm message that are signed or encrypted

```typescript
import { isPresentationRequestJwm } from "wallet-sdk-react-native";
const openResult = await wallet.did.messaging.openDidCommMessage(message);
if (openResult.isErr()) {
  // Handle error from openResult.error
  return;
}
```

## Web Semantic Credential

Verify a Web Semantic credential

```typescript
const verifyResult = await wallet.credential.webSemantic.verifyCredential({ credential });

if (verifyResult.isErr()) {
  // Handle error from verifyResult.error
  return;
}

const { credentialVerified, status } = verifyResult.value;
```

Parse a presentation request (DIDComm message)

```typescript
import { isPresentationRequestJwm } from "wallet-sdk-react-native";
const openResult = await wallet.did.messaging.openDidCommMessage(message);

if (openResult.isErr() || !isPresentationRequestJwm(openResult.value)) {
  return;
}

const presentationRequest = openResult.value;
```

Look up for matching credentials of a presentation request

```typescript
const credentialData = [
  { id: "a", credential: credentailA },
  { id: "b", credential: credentailB },
];

const filterResult = await wallet.credential.webSemantic.filterCredentialsByQuery({
  credentials: credentialData,
  // Note that only the presentation request body should contain single query only, under the same query could contain multiple sub queries.
  query: presentationRequest.body.query[0],
});
```

Create and send a presentation response for a presenation request

```typescript
const createPresentationResult = await wallet.credential.webSemantic.createPresentation({
  challenge: presentationRequest.body.challenge,
  domain: presentationRequest.body.domain,
  credentials,
  holder: did,
});

if (createPresentationResult.isErr()) {
  // Handle error from createPresentationResult.error
  return;
}

const presentaiton = createPresentationResult.value;
const sendPresentationResult = await wallet.credential.webSemantic.sendPresentationResponse({
  presentationRequest,
  presentation,
});
```

## Compact Credential

Verify a compact credential

```typescript
const credentialPayload = "CSC:/1/....";
const verifyResult = await wallet.credential.compact.verifyCredential({ payload: credentialPayload });

if (verifyResult.isErr()) {
  // Handle error from verifyResult.error
  return;
}

if (result.value.verified) {
  const { payload } = result.value;
} else {
  const { reason } = result.value;
}
```

## Compact Semantic Credential

Verify a compact semantic credential

```typescript
const credentialPayload = "CSS:/1/....";
const verifyResult = await wallet.credential.compactSemantic.verifyCredential({ payload: credentialPayload });

if (verifyResult.isErr()) {
  // Handle error from verifyResult.error
  return;
}

if (result.value.verified) {
  const { payload } = result.value;
} else {
  const { reason } = result.value;
}
```

## Mobile Credential

`@mattrglobal/wallet-sdk-react-native` does not come in mobile credential support by default. To enable the mobile
credential feature, an additional peer dependency `@mattrglobal/mobile-credential-holder-react-native` is needed.
Install the following dependency in your app.

> NOTE: mobile credential presentation utilise Bluetooth connection. For iOS make sure the
> `NSBluetoothAlwaysUsageDescription` and `NSBluetoothPeripheralUsageDescription` description are configured inside
> `Info.plist`.

```shell
yarn add @mattrglobal/mobile-credential-holder-react-native@1.0.0
```

include the mobile credential holder extension during initialisation

```typescript
import { initialise } from "@mattrglobal/wallet-sdk-react-native";
import MobileCredentialHolder from "@mattrglobal/mobile-credential-holder-react-native";

await initialise({ extensions: [MobileCredentialHolder], walletId });
```

the same extension is also required while destoying an wallet instance too

```typescript
import { destroy } from "@mattrglobal/wallet-sdk-react-native";
import MobileCredentialHolder from "@mattrglobal/mobile-credential-holder-react-native";

await destroy({ extensions: [MobileCredentialHolder], walletId });
```

With the mobile credential holder extension, the SDK will be able to retrieve mobile credentials over
[OpenID4VCI](#retrieving-credentials-via-openid4vci).

```typescript
import { CredentialProfileSupported } from "@mattrglobal/wallet-sdk-react-native";
const retrieveCredentialsResult = await wallet.openid.issuance.retrieveCredentials({
  offer, // offer that contains mobile credentials
  accessToken,
  clientId,
});

retrieveCredentialsResult.forEach((credentialOfferResult) => {
  if ("error" in credentialOfferResult) {
    const { offer, error } = credentialOfferResult;
    // Handle error from retrieveCredentialsResult.error
  } else {
    const { offer, result } = credentialOfferResult;
    if (result.profile === CredentialProfileSupported.Mobile) {
      const credentialId = result.credentialId;
    }
  }
});
```

The SDK manages the storage of any retrieved mobile credential. They will be accessible via the following mobile
credential functions.

```typescript
// Get a mobile credential
const getCredentialResult = await wallet.credential.mobile.getCredential(credentialId);

// Get all mobile credentials
const getCredentialsResult = await wallet.credential.mobile.getCredentials();

// Delete a mobile credential
await wallet.credential.mobile.deleteCredential(credentialId);
```

The SDK only accept a mobile credential that can be verified successsfully by the trusted issuer certificates. The
trusted issuer certificates list can be managed directly with the following functions

```typescript
// Add new trusted issuer certificates
await wallet.credential.mobile.addTrustedIssuerCertificates(certificates);

// Get all trusted certificates
const certificates = await wallet.credential.mobile.getTrustedIssuerCertificates();

// Rmove one of the trusted issuer certificate
await wallet.credential.mobile.deleteTrustedIssuerCertificate(id);
```

You may also instruct the SDK to automatically download and add certificates if it's discoverable via the openid
credential issuer metadata into the trusted list while retrieving a mobile credential via OpenID4VCI.

```typescript
const retrieveCredentialsResult = await wallet.openid.issuance.retrieveCredentials({
  offer, // offer that contains mobile credentials
  accessToken,
  clientId,
  autoTrustMobileCredentialIaca: true, // enable auto trust
});
```

Mobile credential support presenting credential to a verifier device via bluetooth. The following example is how you
could start and response to a credential presenation request from a verifier device.

> NOTE: Only one presentation session is allowed at a time, you must terminate the current session if you want to start
> a new one.

> NOTE: When a request is received, you must response to it before a new request can come in in the same session.

```typescript
// start a new presentation session
const createPresentationSessionResult = await wallet.credential.mobile.createProximityPresentationSession({
  onRequestReceived: (data) => {
    // request received with error
    if ("error" in data) {
      const { error } = data;
      return;
    }

    const requests = data.request;
    requests.map(({ request, matchedCredentials }) => {
      // obtain each request with matching credentials in the mobile credential store
    });
  },
  onConnected: (data: unknown) => {
    // presentation session is connected
  },
  onSessionTerminated: (data: unknown) => {
    // presentation session is terminated
  },
});

if (createPresentationSessionResult.isErr()) {
  // handle error creating presentation session
}

const { deviceEngagement } = createPresentationSessionResult.value;
// Render device engagement string on a QRCode. A verifier app should scan and use it to establish the presentation session with this holder.

// ....

// construct and send a presentation response with the selected credentials
await wallet.credential.mobile.sendProximityPresentationResponse({ credentialIds });

// ...

// terminate the session
await wallet.credential.mobile.terminateProximityPresentationSession();
```

## Error handling

Functions that are expected to have an error path return a
[Neverthrow Result](https://www.npmjs.com/package/neverthrow#synchronous-api-result) type that represents either success
(`Ok`) or failure (`Err`).

Although this pattern is more verbose, it encourages the handling of possibly errors and reserves throwing exceptions
for truly exceptional situations.

```typescript
import { initialise } from "@mattrglobal/wallet-sdk-react-native";

const initialiseWalletResult = await initialise();

if (initialiseWalletResult.isErr()) {
  // Handle error from initialiseWalletResult.error
  return;
}

const wallet = initialiseWalletResult.value;
```

### unwrap

A utility function is provided for convenience if you decide not to handle your errors as results. This function will
simply throw an error if the function passed in returns a `Result` where `Resut.isErr()` is true.

```typescript
import { unwrap } from "@mattrglobal/wallet-sdk-react-native";

try {
  const wallet = unwrap(await initialise());
} catch (error) {
  // Handle thrown error
}
```

## Licensing

See [here](https://learn.mattr.global/docs/terms/mattr-pi-sdk-licence-agreement) for licence information
