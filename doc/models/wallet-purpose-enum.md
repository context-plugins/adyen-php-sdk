
# Wallet Purpose Enum

The purpose of a digital wallet transaction.

## Enumeration

`WalletPurposeEnum`

## Fields

| Name |
|  --- |
| `IDENTIFIEDBOLETO` |
| `TRANSFERDIFFERENTWALLET` |
| `TRANSFEROWNWALLET` |
| `TRANSFERSAMEWALLET` |
| `UNIDENTIFIEDBOLETO` |

## Example

```php
use AdyenLib\Models\WalletPurposeEnum;

$walletPurpose = WalletPurposeEnum::TRANSFEROWNWALLET;
```

