
# Affirm Update Info

## Structure

`AffirmUpdateInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pricePlan` | `?string` | Optional | Selected Affirm financing package. Choose from **core**, **standard**, or **signature**. Defaults to **core** if no selection made. | getPricePlan(): ?string | setPricePlan(?string pricePlan): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmUpdateInfoBuilder;

$affirmUpdateInfo = AffirmUpdateInfoBuilder::init()
    ->pricePlan('pricePlan2')
    ->build();
```

