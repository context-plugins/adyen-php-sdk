
# Pay to Info

## Structure

`PayToInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantName` | `string` | Required | Merchant name displayed to the shopper in the Agreements | getMerchantName(): string | setMerchantName(string merchantName): void |
| `payToPurpose` | `string` | Required | Represents the purpose of the Agreements created, it relates to the business type<br>**Allowed values**: mortgage, utility, loan, gambling, retail, salary, personal, government, pension, tax, other | getPayToPurpose(): string | setPayToPurpose(string payToPurpose): void |

## Example

```php
use AdyenLib\Models\Builders\PayToInfoBuilder;

$payToInfo = PayToInfoBuilder::init(
    'merchantName8',
    'payToPurpose6'
)->build();
```

