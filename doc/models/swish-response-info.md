
# Swish Response Info

## Structure

`SwishResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `swishNumber` | `?string` | Optional | Swish number. Format: 10 digits without spaces. For example, **1231111111**.<br><br>**Constraints**: *Minimum Length*: `10`, *Maximum Length*: `10` | getSwishNumber(): ?string | setSwishNumber(?string swishNumber): void |

## Example

```php
use AdyenLib\Models\Builders\SwishResponseInfoBuilder;

$swishResponseInfo = SwishResponseInfoBuilder::init()
    ->swishNumber('swishNumber4')
    ->build();
```

