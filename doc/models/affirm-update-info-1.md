
# Affirm Update Info 1

Details to provide if `type` is **affirm**.

## Structure

`AffirmUpdateInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pricePlan` | `?string` | Optional | Selected Affirm financing package. Choose from **core**, **standard**, or **signature**. Defaults to **core** if no selection made. | getPricePlan(): ?string | setPricePlan(?string pricePlan): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmUpdateInfo1Builder;

$affirmUpdateInfo1 = AffirmUpdateInfo1Builder::init()
    ->pricePlan('pricePlan2')
    ->build();
```

