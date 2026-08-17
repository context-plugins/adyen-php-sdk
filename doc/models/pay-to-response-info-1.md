
# Pay to Response Info 1

**payto** details

## Structure

`PayToResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantName` | `?string` | Optional | Merchant name displayed to the shopper in the Agreements | getMerchantName(): ?string | setMerchantName(?string merchantName): void |
| `payToPurpose` | `?string` | Optional | Represents the purpose of the Agreements created, it relates to the business type<br>**Allowed values**: mortgage, utility, loan, gambling, retail, salary, personal, government, pension, tax, other | getPayToPurpose(): ?string | setPayToPurpose(?string payToPurpose): void |

## Example

```php
use AdyenLib\Models\Builders\PayToResponseInfo1Builder;

$payToResponseInfo1 = PayToResponseInfo1Builder::init()
    ->merchantName('merchantName0')
    ->payToPurpose('payToPurpose6')
    ->build();
```

