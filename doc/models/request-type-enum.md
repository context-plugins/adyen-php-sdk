
# Request Type Enum

Indicates the type of request to which the rule applies. If not provided, by default, this is set to **authorization**.

Possible values: **authorization**, **authentication**, **tokenization**, **bankTransfer**.

## Enumeration

`RequestTypeEnum`

## Fields

| Name |
|  --- |
| `AUTHENTICATION` |
| `AUTHORIZATION` |
| `BANKTRANSFER` |
| `TOKENIZATION` |

## Example

```php
use AdyenLib\Models\RequestTypeEnum;

$requestType = RequestTypeEnum::BANKTRANSFER;
```

