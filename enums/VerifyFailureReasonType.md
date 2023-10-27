[MATTR Wallet SDK React Native](../README.md) / [Exports](../modules.md) / VerifyFailureReasonType

# Enumeration: VerifyFailureReasonType

## Table of contents

### Enumeration Members

- [Expired](VerifyFailureReasonType.md#expired)
- [IssuerNotTrusted](VerifyFailureReasonType.md#issuernottrusted)
- [IssuerPublicKeyInvalid](VerifyFailureReasonType.md#issuerpublickeyinvalid)
- [NotActive](VerifyFailureReasonType.md#notactive)
- [PayloadInvalid](VerifyFailureReasonType.md#payloadinvalid)
- [Revoked](VerifyFailureReasonType.md#revoked)
- [SignatureInvalid](VerifyFailureReasonType.md#signatureinvalid)
- [UnsupportedAlgorithm](VerifyFailureReasonType.md#unsupportedalgorithm)
- [UnsupportedRevocationType](VerifyFailureReasonType.md#unsupportedrevocationtype)

## Enumeration Members

### Expired

• **Expired** = ``"Expired"``

Credential is expired

___

### IssuerNotTrusted

• **IssuerNotTrusted** = ``"IssuerNotTrusted"``

Issuer of the credential is not trusted

___

### IssuerPublicKeyInvalid

• **IssuerPublicKeyInvalid** = ``"IssuerPublicKeyInvalid"``

Invalid issuer public key

___

### NotActive

• **NotActive** = ``"NotActive"``

Credential are not active

___

### PayloadInvalid

• **PayloadInvalid** = ``"PayloadInvalid"``

Credential payload is malformed

___

### Revoked

• **Revoked** = ``"Revoked"``

Credential has been revoked

___

### SignatureInvalid

• **SignatureInvalid** = ``"SignatureInvalid"``

The signature of the credential is invalid

___

### UnsupportedAlgorithm

• **UnsupportedAlgorithm** = ``"UnsupportedAlgorithm"``

Payload COSE encoded with an unsupported algorithm

___

### UnsupportedRevocationType

• **UnsupportedRevocationType** = ``"UnsupportedRevocationType"``

Payload revocation encoded with an unsupported type
