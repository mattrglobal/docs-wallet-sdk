Mattr Wallet SDK React Native / [Exports](modules.md)

# wallet-sdk-react-native

## Usage

### Install dependencies

Add this SDK as a dependency to the react native app

```
yarn add @mattrglobal/wallet-sdk-react-native
```

Add the required peer dependencies for the sake of auto linking

```
yarn add react-native-securerandom@1.0.0 realm@10.4.0 react-native-fs@2.17.0 react-native-secure-key-store@2.0.9 @mattrglobal/rn-bbs-signature@0.1.0
```

### Configure metro bbs-signatures mapping

Add a extraNodeModules mapping entry, and a blacklistRE record for bbs-signatures to `metro.config.js`. For versions
<0.59 please refer to
[this stack overflow answer](https://stackoverflow.com/questions/41813211/how-to-make-react-native-packager-ignore-certain-directories/41963217#41963217)
for instructions on defining an exclusion list

```
// For React Native >= 0.64
const exclusionList = require('metro-config/src/defaults/exclusionList');

// For React Native >= 0.59, < 0.64
const exclusionList = require("metro-config/src/defaults/blacklist");
```

Define the following `blacklistRE` regex and `extraNodeModules` entry

```
module.exports = {
    ...
    resolver: {
       blacklistRE: exclusionList([/.*mattrglobal\/bbs-signatures.*/]),
       extraNodeModules: {
          "@mattrglobal/bbs-signatures": "./node_modules/@mattrglobal/rn-bbs-signatures",
      },
    },
    ...
};
```

### Android only

make sure the following repository is included under `android/build.gradle` `allprojects.repositories`

```
allprojects {
    repositories {
        ...
        maven { url 'https://oss.sonatype.org/content/repositories/snapshots/' }
        ...
    }
}
```

### iOS only

Add the pod for bbs-signatures to the podfile in `ios/Podfile`

```
  pod 'bbs-signatures', :git => 'https://github.com/mattrglobal/ffi-bbs-signatures'
```

Run pod install

```
cd ios && pod install
```
