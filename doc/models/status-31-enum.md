
# Status 31 Enum

On a terminal that supports 3G or 4G connectivity, indicates the status of the primary SIM card in the terminal.

## Enumeration

`Status31Enum`

## Fields

| Name |
|  --- |
| `ACTIVATED` |
| `DEACTIVATED` |
| `DEPRECATED` |
| `INVENTORY` |
| `READYFORACTIVATION` |

## Example

```php
use AdyenLib\Models\Status31Enum;

$status31 = Status31Enum::READYFORACTIVATION;
```

