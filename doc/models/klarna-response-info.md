
# Klarna Response Info

## Structure

`KlarnaResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoCapture` | `?bool` | Optional | Indicates the status of [Automatic capture](https://docs.adyen.com/online-payments/capture#automatic-capture). | getAutoCapture(): ?bool | setAutoCapture(?bool autoCapture): void |
| `disputeEmail` | `?string` | Optional | The email address for disputes. | getDisputeEmail(): ?string | setDisputeEmail(?string disputeEmail): void |
| `region` | [`?string(Region1Enum)`](../../doc/models/region-1-enum.md) | Optional | The region of operation. | getRegion(): ?string | setRegion(?string region): void |
| `supportEmail` | `?string` | Optional | The email address of merchant support. | getSupportEmail(): ?string | setSupportEmail(?string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\KlarnaResponseInfoBuilder;
use AdyenLib\Models\Region1Enum;

$klarnaResponseInfo = KlarnaResponseInfoBuilder::init()
    ->autoCapture(false)
    ->disputeEmail('disputeEmail6')
    ->region(Region1Enum::AU)
    ->supportEmail('supportEmail0')
    ->build();
```

