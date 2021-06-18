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
