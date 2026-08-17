
# Swish Response Info 2

**swish** or its variant details

## Structure

`SwishResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `swishNumber` | `?string` | Optional | Swish number. Format: 10 digits without spaces. For example, **1231111111**.<br><br>**Constraints**: *Minimum Length*: `10`, *Maximum Length*: `10` | getSwishNumber(): ?string | setSwishNumber(?string swishNumber): void |

## Example

```php
use AdyenLib\Models\Builders\SwishResponseInfo2Builder;

$swishResponseInfo2 = SwishResponseInfo2Builder::init()
    ->swishNumber('swishNumber0')
    ->build();
```

