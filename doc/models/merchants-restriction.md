
# Merchants Restriction

## Structure

`MerchantsRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(MerchantAcquirerPair[])`](../../doc/models/merchant-acquirer-pair.md) | Optional | List of merchant ID and acquirer ID pairs. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantsRestrictionBuilder;
use AdyenLib\Models\Builders\MerchantAcquirerPairBuilder;

$merchantsRestriction = MerchantsRestrictionBuilder::init(
    'operation0'
)
    ->value(
        [
            MerchantAcquirerPairBuilder::init()
                ->acquirerId('acquirerId4')
                ->merchantId('merchantId8')
                ->build(),
            MerchantAcquirerPairBuilder::init()
                ->acquirerId('acquirerId4')
                ->merchantId('merchantId8')
                ->build()
        ]
    )
    ->build();
```

