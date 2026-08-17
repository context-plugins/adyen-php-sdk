
# Three DS 2 Response Data 1

Response of the 3D Secure 2 authentication.

## Structure

`ThreeDS2ResponseData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acsChallengeMandated` | `?string` | Optional | - | getAcsChallengeMandated(): ?string | setAcsChallengeMandated(?string acsChallengeMandated): void |
| `acsOperatorID` | `?string` | Optional | - | getAcsOperatorID(): ?string | setAcsOperatorID(?string acsOperatorID): void |
| `acsReferenceNumber` | `?string` | Optional | - | getAcsReferenceNumber(): ?string | setAcsReferenceNumber(?string acsReferenceNumber): void |
| `acsSignedContent` | `?string` | Optional | - | getAcsSignedContent(): ?string | setAcsSignedContent(?string acsSignedContent): void |
| `acsTransID` | `?string` | Optional | - | getAcsTransID(): ?string | setAcsTransID(?string acsTransID): void |
| `acsURL` | `?string` | Optional | - | getAcsURL(): ?string | setAcsURL(?string acsURL): void |
| `authenticationType` | `?string` | Optional | - | getAuthenticationType(): ?string | setAuthenticationType(?string authenticationType): void |
| `cardHolderInfo` | `?string` | Optional | - | getCardHolderInfo(): ?string | setCardHolderInfo(?string cardHolderInfo): void |
| `cavvAlgorithm` | `?string` | Optional | - | getCavvAlgorithm(): ?string | setCavvAlgorithm(?string cavvAlgorithm): void |
| `challengeIndicator` | `?string` | Optional | - | getChallengeIndicator(): ?string | setChallengeIndicator(?string challengeIndicator): void |
| `dsReferenceNumber` | `?string` | Optional | - | getDsReferenceNumber(): ?string | setDsReferenceNumber(?string dsReferenceNumber): void |
| `dsTransID` | `?string` | Optional | - | getDsTransID(): ?string | setDsTransID(?string dsTransID): void |
| `exemptionIndicator` | `?string` | Optional | - | getExemptionIndicator(): ?string | setExemptionIndicator(?string exemptionIndicator): void |
| `messageVersion` | `?string` | Optional | - | getMessageVersion(): ?string | setMessageVersion(?string messageVersion): void |
| `riskScore` | `?string` | Optional | - | getRiskScore(): ?string | setRiskScore(?string riskScore): void |
| `sdkEphemPubKey` | `?string` | Optional | - | getSdkEphemPubKey(): ?string | setSdkEphemPubKey(?string sdkEphemPubKey): void |
| `threeDSServerTransID` | `?string` | Optional | - | getThreeDSServerTransID(): ?string | setThreeDSServerTransID(?string threeDSServerTransID): void |
| `transStatus` | `?string` | Optional | - | getTransStatus(): ?string | setTransStatus(?string transStatus): void |
| `transStatusReason` | `?string` | Optional | - | getTransStatusReason(): ?string | setTransStatusReason(?string transStatusReason): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDS2ResponseData1Builder;

$threeDS2ResponseData1 = ThreeDS2ResponseData1Builder::init()
    ->acsChallengeMandated('acsChallengeMandated0')
    ->acsOperatorID('acsOperatorID0')
    ->acsReferenceNumber('acsReferenceNumber0')
    ->acsSignedContent('acsSignedContent6')
    ->acsTransID('acsTransID0')
    ->build();
```

