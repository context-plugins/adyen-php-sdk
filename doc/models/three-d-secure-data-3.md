
# Three D Secure Data 3

Authentication data from a [merchant plug-in (MPI)](https://en.wikipedia.org/wiki/Merchant_plug-in) like Mastercard SecureCode, Visa Secure, or Cartes Bancaires. Required for cardholder-initiated transaction (CIT) adjustments.

## Structure

`ThreeDSecureData3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authenticationResponse` | [`?string(AuthenticationResponseEnum)`](../../doc/models/authentication-response-enum.md) | Optional | In 3D Secure 2, this is the `transStatus` from the challenge result. If the transaction was frictionless, omit this parameter. | getAuthenticationResponse(): ?string | setAuthenticationResponse(?string authenticationResponse): void |
| `cavv` | `?string` | Optional | The cardholder authentication value (base64 encoded, 20 bytes in a decoded form). | getCavv(): ?string | setCavv(?string cavv): void |
| `cavvAlgorithm` | `?string` | Optional | The CAVV algorithm used. Include this only for 3D Secure 1. | getCavvAlgorithm(): ?string | setCavvAlgorithm(?string cavvAlgorithm): void |
| `challengeCancel` | [`?string(ChallengeCancelEnum)`](../../doc/models/challenge-cancel-enum.md) | Optional | Indicator informing the Access Control Server (ACS) and the Directory Server (DS) that the authentication has been cancelled. For possible values, refer to [3D Secure API reference](https://docs.adyen.com/online-payments/3d-secure/api-reference#mpidata). | getChallengeCancel(): ?string | setChallengeCancel(?string challengeCancel): void |
| `directoryResponse` | [`?string(DirectoryResponseEnum)`](../../doc/models/directory-response-enum.md) | Optional | In 3D Secure 2, this is the `transStatus` from the `ARes`. | getDirectoryResponse(): ?string | setDirectoryResponse(?string directoryResponse): void |
| `dsTransID` | `?string` | Optional | Supported for 3D Secure 2. The unique transaction identifier assigned by the Directory Server (DS) to identify a single transaction. | getDsTransID(): ?string | setDsTransID(?string dsTransID): void |
| `eci` | `?string` | Optional | The electronic commerce indicator. | getEci(): ?string | setEci(?string eci): void |
| `riskScore` | `?string` | Optional | Risk score calculated by Directory Server (DS). Required for Cartes Bancaires integrations. | getRiskScore(): ?string | setRiskScore(?string riskScore): void |
| `threeDSVersion` | `?string` | Optional | The version of the 3D Secure protocol. | getThreeDSVersion(): ?string | setThreeDSVersion(?string threeDSVersion): void |
| `tokenAuthenticationVerificationValue` | `?string` | Optional | Network token authentication verification value (TAVV). The network token cryptogram. | getTokenAuthenticationVerificationValue(): ?string | setTokenAuthenticationVerificationValue(?string tokenAuthenticationVerificationValue): void |
| `transStatusReason` | `?string` | Optional | Provides information on why the `transStatus` field has the specified value. For possible values, refer to [our docs](https://docs.adyen.com/online-payments/3d-secure/api-reference#possible-transstatusreason-values). | getTransStatusReason(): ?string | setTransStatusReason(?string transStatusReason): void |
| `xid` | `?string` | Optional | Supported for 3D Secure 1. The transaction identifier (Base64-encoded, 20 bytes in a decoded form). | getXid(): ?string | setXid(?string xid): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSecureData3Builder;
use AdyenLib\Models\AuthenticationResponseEnum;
use AdyenLib\Models\ChallengeCancelEnum;
use AdyenLib\Models\DirectoryResponseEnum;

$threeDSecureData3 = ThreeDSecureData3Builder::init()
    ->authenticationResponse(AuthenticationResponseEnum::Y)
    ->cavv('cavv4')
    ->cavvAlgorithm('cavvAlgorithm6')
    ->challengeCancel(ChallengeCancelEnum::ENUM_05)
    ->directoryResponse(DirectoryResponseEnum::A)
    ->build();
```

