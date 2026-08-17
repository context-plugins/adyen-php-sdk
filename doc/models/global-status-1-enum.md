
# Global Status 1 Enum

Global status of a POI Server or POI Terminal.
Possible values:

* **Busy**
* **Maintenance**
* **OK**
* **Unreachable**

## Enumeration

`GlobalStatus1Enum`

## Fields

| Name |
|  --- |
| `OK` |
| `BUSY` |
| `MAINTENANCE` |
| `UNREACHABLE` |

## Example

```php
use AdyenLib\Models\GlobalStatus1Enum;

$globalStatus1 = GlobalStatus1Enum::MAINTENANCE;
```

