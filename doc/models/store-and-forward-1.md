
# Store and Forward 1

Settings for store-and-forward offline payments. The `maxAmount`, `maxPayments`, and `supportedCardTypes` parameters must be configured, either in the request or inherited from a higher level in your account structure.

## Structure

`StoreAndForward1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maxAmount` | [`?(MinorUnitsMonetaryValue[])`](../../doc/models/minor-units-monetary-value.md) | Optional | The maximum amount that the terminal accepts for a single store-and-forward payment. | getMaxAmount(): ?array | setMaxAmount(?array maxAmount): void |
| `maxPayments` | `?int` | Optional | The maximum number of store-and-forward transactions per terminal that you can process while offline. | getMaxPayments(): ?int | setMaxPayments(?int maxPayments): void |
| `supportedCardTypes` | [`?SupportedCardTypes2`](../../doc/models/supported-card-types-2.md) | Optional | The type of card for which the terminal accepts store-and-forward payments. You can specify multiple card types. | getSupportedCardTypes(): ?SupportedCardTypes2 | setSupportedCardTypes(?SupportedCardTypes2 supportedCardTypes): void |

## Example

```php
use AdyenLib\Models\Builders\StoreAndForward1Builder;
use AdyenLib\Models\Builders\MinorUnitsMonetaryValueBuilder;
use AdyenLib\Models\Builders\SupportedCardTypes2Builder;

$storeAndForward1 = StoreAndForward1Builder::init()
    ->maxAmount(
        [
            MinorUnitsMonetaryValueBuilder::init()
                ->amount(50)
                ->currencyCode('currencyCode4')
                ->build(),
            MinorUnitsMonetaryValueBuilder::init()
                ->amount(50)
                ->currencyCode('currencyCode4')
                ->build(),
            MinorUnitsMonetaryValueBuilder::init()
                ->amount(50)
                ->currencyCode('currencyCode4')
                ->build()
        ]
    )
    ->maxPayments(44)
    ->supportedCardTypes(
        SupportedCardTypes2Builder::init()
            ->credit(false)
            ->debit(false)
            ->deferredDebit(false)
            ->prepaid(false)
            ->unknown(false)
            ->build()
    )
    ->build();
```

