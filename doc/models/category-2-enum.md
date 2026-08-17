
# Category 2 Enum

The type of transfer.

Possible values:

- **bank**: Transfer to a [transfer instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments__resParam_id) or a bank account.

## Enumeration

`Category2Enum`

## Fields

| Name |
|  --- |
| `BANK` |
| `CARD` |
| `GRANTS` |
| `INTEREST` |
| `INTERNAL` |
| `ISSUEDCARD` |
| `MIGRATION` |
| `PLATFORMPAYMENT` |
| `TOPUP` |
| `UPGRADE` |

## Example

```php
use AdyenLib\Models\Category2Enum;

$category2 = Category2Enum::GRANTS;
```

