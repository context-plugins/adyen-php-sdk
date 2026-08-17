
# Response Additional Data Swish

## Structure

`ResponseAdditionalDataSwish`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `swishPayerAlias` | `?string` | Optional | A Swish shopper's telephone number. | getSwishPayerAlias(): ?string | setSwishPayerAlias(?string swishPayerAlias): void |

## Example

```php
use AdyenLib\Models\Builders\ResponseAdditionalDataSwishBuilder;

$responseAdditionalDataSwish = ResponseAdditionalDataSwishBuilder::init()
    ->swishPayerAlias('swish.payerAlias8')
    ->build();
```

