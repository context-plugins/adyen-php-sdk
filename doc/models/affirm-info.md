
# Affirm Info

## Structure

`AffirmInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pricePlan` | `?string` | Optional | Selected Affirm financing package. Choose from **core**, **standard**, or **signature**. Defaults to **core** if no selection made. | getPricePlan(): ?string | setPricePlan(?string pricePlan): void |
| `supportEmail` | `string` | Required | Merchant support email used to manage disputes. | getSupportEmail(): string | setSupportEmail(string supportEmail): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmInfoBuilder;

$affirmInfo = AffirmInfoBuilder::init(
    'supportEmail6'
)
    ->pricePlan('pricePlan4')
    ->build();
```

