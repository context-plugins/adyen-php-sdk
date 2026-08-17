
# Three DS Requestor Prior Authentication Info

Information about how the 3DS Requestor authenticated the cardholder as part of a previous 3DS transaction.

## Structure

`ThreeDSRequestorPriorAuthenticationInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `threeDSReqPriorAuthData` | `?string` | Optional | Data that documents and supports a specific authentication process. Maximum length: 2048 bytes. | getThreeDSReqPriorAuthData(): ?string | setThreeDSReqPriorAuthData(?string threeDSReqPriorAuthData): void |
| `threeDSReqPriorAuthMethod` | [`?string(ThreeDSReqPriorAuthMethodEnum)`](../../doc/models/three-ds-req-prior-auth-method-enum.md) | Optional | Mechanism used by the Cardholder to previously authenticate to the 3DS Requestor. Allowed values:<br><br>* **01** — Frictionless authentication occurred by ACS.<br>* **02** — Cardholder challenge occurred by ACS.<br>* **03** — AVS verified.<br>* **04** — Other issuer methods.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getThreeDSReqPriorAuthMethod(): ?string | setThreeDSReqPriorAuthMethod(?string threeDSReqPriorAuthMethod): void |
| `threeDSReqPriorAuthTimestamp` | `?string` | Optional | Date and time in UTC of the prior cardholder authentication. Format: YYYYMMDDHHMM<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `12` | getThreeDSReqPriorAuthTimestamp(): ?string | setThreeDSReqPriorAuthTimestamp(?string threeDSReqPriorAuthTimestamp): void |
| `threeDSReqPriorRef` | `?string` | Optional | This data element provides additional information to the ACS to determine the best approach for handing a request. This data element contains an ACS Transaction ID for a prior authenticated transaction. For example, the first recurring transaction that was authenticated with the cardholder. Length: 30 characters.<br><br>**Constraints**: *Minimum Length*: `36`, *Maximum Length*: `36` | getThreeDSReqPriorRef(): ?string | setThreeDSReqPriorRef(?string threeDSReqPriorRef): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSRequestorPriorAuthenticationInfoBuilder;
use AdyenLib\Models\ThreeDSReqPriorAuthMethodEnum;

$threeDSRequestorPriorAuthenticationInfo = ThreeDSRequestorPriorAuthenticationInfoBuilder::init()
    ->threeDSReqPriorAuthData('threeDSReqPriorAuthData2')
    ->threeDSReqPriorAuthMethod(ThreeDSReqPriorAuthMethodEnum::ENUM_01)
    ->threeDSReqPriorAuthTimestamp('threeDSReqPriorAuthTimestamp0')
    ->threeDSReqPriorRef('threeDSReqPriorRef2')
    ->build();
```

