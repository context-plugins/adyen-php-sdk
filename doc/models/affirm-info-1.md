
# Affirm Info 1

Details to provide if `type` is **affirm**.

## Structure

`AffirmInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pricePlan` | `?string` | Optional | Selected Affirm financing package. Choose from **core**, **standard**, or **signature**. Defaults to **core** if no selection made. | getPricePlan(): ?string | setPricePlan(?string pricePlan): void |
| `supportEmail` | `string` | Required | Merchant support email used to manage disputes. | getSupportEmail(): string | setSupportEmail(string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmInfo1Builder;

$affirmInfo1 = AffirmInfo1Builder::init(
    'supportEmail2'
)
    ->pricePlan('pricePlan8')
    ->build();
```

