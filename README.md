Mattr Wallet SDK React Native / [Exports](modules.md)

# wallet-sdk-react-native

# Table of Contents

- [Features](#features)
- [Getting started](#getting-started)
- [Usage](#usage)
  - [Codec](#codec)
  - [Wallet](#wallet)
  - [Error handling](#error-handling)

# Features

- Codec operations
- Manage DIDs
- Filter, derive and verify credentials
- Discover, request and retrieve credentials from oidc providers
- Validate a DID to domain linkage with wellKnownDidConfiguration
- Create and send presentation request responses
- DIDComm messaging

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
yarn add react-native-securerandom@1.0.0 realm@10.4.0 react-native-fs@2.17.0 react-native-secure-key-store@2.0.9 @mattrglobal/rn-bbs-signature@0.1.0
```

### React Native <0.60

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

const did = createDidResult.value;
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
