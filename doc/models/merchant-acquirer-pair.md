
# Merchant Acquirer Pair

## Structure

`MerchantAcquirerPair`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerId` | `?string` | Optional | The acquirer ID. | getAcquirerId(): ?string | setAcquirerId(?string acquirerId): void |
| `merchantId` | `?string` | Optional | The merchant identification number (MID). | getMerchantId(): ?string | setMerchantId(?string merchantId): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantAcquirerPairBuilder;

$merchantAcquirerPair = MerchantAcquirerPairBuilder::init()
    ->acquirerId('acquirerId0')
    ->merchantId('merchantId4')
    ->build();
```

