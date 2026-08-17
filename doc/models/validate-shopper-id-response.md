
# Validate Shopper Id Response

## Structure

`ValidateShopperIdResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Reason for the result. | getReason(): ?string | setReason(?string reason): void |
| `result` | [`?string(Result1Enum)`](../../doc/models/result-1-enum.md) | Optional | Result of the validation. Ex: valid, invalid, unknown | getResult(): ?string | setResult(?string result): void |

## Example

```php
use AdyenLib\Models\Builders\ValidateShopperIdResponseBuilder;
use AdyenLib\Models\Result1Enum;

$validateShopperIdResponse = ValidateShopperIdResponseBuilder::init()
    ->reason('reason2')
    ->result(Result1Enum::VALID)
    ->build();
```

