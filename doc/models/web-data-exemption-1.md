
# Web Data Exemption 1

The reason why the web data is not provided.

## Structure

`WebDataExemption1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | [`?string(Reason3Enum)`](../../doc/models/reason-3-enum.md) | Optional | The reason why the web data was not provided. Possible value: **noOnlinePresence**. | getReason(): ?string | setReason(?string reason): void |

## Example

```php
use AdyenLib\Models\Builders\WebDataExemption1Builder;
use AdyenLib\Models\Reason3Enum;

$webDataExemption1 = WebDataExemption1Builder::init()
    ->reason(Reason3Enum::NOONLINEPRESENCE)
    ->build();
```

