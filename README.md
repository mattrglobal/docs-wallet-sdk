Mattr Wallet SDK React Native / [Exports](modules.md)

# wallet-sdk-react-native

# Table of Contents

- [Features](#features)
- [Getting started](#getting-started)
- [Usage](#usage)
  - [Codec](#codec)
  - [Wallet](#wallet)
  - [Retrieving credentials via OIDC](#retrieving-credentials-via-oidc)
  - [Retrieving credentials via OpenId issuance](#retrieving-credentials-via-openid-issuance)
  - [Handling a credential presentation request DidComm message](#handling-a-credential-presentation-request-didcomm-message)
  - [Error handling](#error-handling)

# Features

- Codec operations
- Manage DIDs
- Filter, derive and verify credentials
- Discover, request and retrieve credentials from oidc providers
- Validate a DID to domain linkage with wellKnownDidConfiguration
- Create and send presentation request responses
- DIDComm messaging

# High level overview

![High Level](./docs/highlevel.drawio.png)

# Getting started

## Install dependencies

Add this SDK as a dependency to the react native app:

```
yarn add @mattrglobal/wallet-sdk-react-native
```

The SDK relies on a set of peer dependencies that contain native libraries and iOS pods. With React Native >=0.60 these
dependencies will be autolinked.

Install the peer dependencies:

```
yarn add react-native-securerandom@1.0.0 realm@10.4.0 react-native-fs@2.17.0 react-native-secure-key-store@2.0.9 @mattrglobal/rn-bbs-signatures@1.0.0 react-native-get-random-values@1.7.0
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

# Usage

## Codec

```typescript
import { codec } from "@mattrglobal/wallet-sdk-react-native";

const bytes = codec.stringToBytes("a string");
```

## Wallet

Create a new wallet:

```typescript
import { create } from "@mattrglobal/wallet-sdk-react-native";

const createWalletResult = await create();

if (createWalletResult.isErr()) {
  // Handle error from createWalletResult.error
  return;
}
```

Open an existing wallet:

```typescript
import { open } from "@mattrglobal/wallet-sdk-react-native";

const openWalletResult = await open();

if (openWalletResult.isErr()) {
  // Handle error from openWalletResult.error
  return;
}

const wallet = openWalletResult.value;
```

Use the open wallet:

```typescript
// Create a new DID
const createDidResult = await wallet.did.create();

if (createDidResult.isErr()) {
  // Handle error from createDidResult.error
  return;
}

const { did } = createDidResult.value;
```

Close the wallet:

```typescript
import { close } from "@mattrglobal/wallet-sdk-react-native";

console.log(wallet.isOpen()); // true

const closeWalletResult = await wallet.close();

if (closeWalletResult.isErr()) {
  // Handle error from closeWalletResult.error
  return;
}

console.log(wallet.isOpen()); // false
```

Destroy the wallet:

```typescript
import { destroy } from "@mattrglobal/wallet-sdk-react-native";

await wallet.destroy();
```

## Retrieving credentials via OIDC

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
const createDidResult = await wallet.did.create();

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

Verify a credential

```typescript
const verifyResult = await wallet.credential.verify({ credential });

if (verifyResult.isErr()) {
  // Handle error from verifyResult.error
  return;
}

const { credentialVerified, status } = verifyResult.value;
```

## Retrieving credentials via openid issuance

Construct an offer payload and set up OAuth client

```typescript
const offer: OpenidIssuanceCredentialOffer = {
  issuer: "https://example.com/",
  authorizeEndpoint: "https://example.com/oauth/authorize",
  tokenEndpoint: "https://example.com/oauth/token",
  credentialEndpoint: "https://example.com/oauth/credential",
  credentials: [
    {
      format: "ldp_vc",
      type: "UniversityDegreeCredential",
      scope: "UniversityDegreeCredential",
    },
  ],
};

const clientId = "myAppClientId";
const redirectUri = "myapp://credentials/callback";
```

Generate an authorization url to initiate an openid issuance flow

```typescript
import { Linking } from "react-native";

const genUrlResult = await wallet.openid.issuance.generateAuthorizeUrl({ offer, clientId, redirectUri });

if (genUrlResult.isErr()) {
  // Handle error from genUrlResult.error
  return;
}

const { url, codeVerifier } = genUrlResult.value;
await Linking.openURL(url);
```

Retrieve the token and credential on authorization success callback

```typescript
const tokenResult = await wallet.openid.issuance.retrieveToken({
  offer,
  codeVerifier,
  code: route.params.code, // code comes from part of the callback url
  redirectUri,
  clientId,
});

if (tokenResult.isErr()) {
  // Handle error from tokenResult.error
  return;
}

const { accessToken } = tokenResult.value;

const retrieveResult = await wallet.openid.issuance.retrieveCredentials({
  offer,
  accessToken,
  clientId,
});

if (retrieveResult.isErr()) {
  // Handle error from retrieveResult.error
  return;
}

retrieveResult.value.credentials.forEach(({ credential, format, did }) => {
  // access to credential
});
```

## Handling a credential presentation request DIDComm message

Open a presentation request DIDComm message

```typescript
import { isPresentationRequestJwm } from "wallet-sdk-react-native";
const openResult = await wallet.messaging.openDidCommMessage(message);

if (openResult.isErr() || !isPresentationRequestJwm(openResult.value)) {
  return;
}

const presentationRequest = openResult.value;
```

Look up for matching credentials

```typescript
const credentialData = [
  { id: "a", credential: credentailA },
  { id: "b", credential: credentailB },
];
const filterResult = await wallet.presentation.filterCredentialsByQuery({ credentials: credentialData });
```

Create and send presentation

```typescript
const createPresentationResult = await wallet.presentation.create({
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
const sendPresentationResult = await wallet.presentation.sendPresentationResponse({
  presentationRequest,
  presentation,
});
```

## Error handling

Functions that are expected to have an error path return a
[Neverthrow Result](https://www.npmjs.com/package/neverthrow#synchronous-api-result) type that represents either success
(`Ok`) or failure (`Err`).

Although this pattern is more verbose, it encourages the handling of possibly errors and reserves throwing exceptions
for truly exceptional situations.

```typescript
import { open } from "@mattrglobal/wallet-sdk-react-native";

const openWalletResult = await open();

if (openWalletResult.isErr()) {
  // Handle error from openWalletResult.error
  return;
}

const wallet = openWalletResult.value;
```

### unwrap

A utility function is provided for convenience if you decide not to handle your errors as results. This function will
simply throw an error if the function passed in returns a `Result` where `Resut.isErr()` is true.

```typescript
import { unwrap } from "@mattrglobal/wallet-sdk-react-native";

try {
  const wallet = unwrap(await open());
} catch (error) {
  // Handle thrown error
}
```

## Licensing

see [here](Licence.pdf) for licence information
