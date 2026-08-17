
# Web Data Exemption

## Structure

`WebDataExemption`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | [`?string(Reason3Enum)`](../../doc/models/reason-3-enum.md) | Optional | The reason why the web data was not provided. Possible value: **noOnlinePresence**. | getReason(): ?string | setReason(?string reason): void |

## Example

```php
use AdyenLib\Models\Builders\WebDataExemptionBuilder;
use AdyenLib\Models\Reason3Enum;

$webDataExemption = WebDataExemptionBuilder::init()
    ->reason(Reason3Enum::NOONLINEPRESENCE)
    ->build();
```

