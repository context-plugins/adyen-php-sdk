
# Store and Forward

## Structure

`StoreAndForward`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maxAmount` | [`?(MinorUnitsMonetaryValue[])`](../../doc/models/minor-units-monetary-value.md) | Optional | The maximum amount that the terminal accepts for a single store-and-forward payment. | getMaxAmount(): ?array | setMaxAmount(?array maxAmount): void |
| `maxPayments` | `?int` | Optional | The maximum number of store-and-forward transactions per terminal that you can process while offline. | getMaxPayments(): ?int | setMaxPayments(?int maxPayments): void |
| `supportedCardTypes` | [`?SupportedCardTypes2`](../../doc/models/supported-card-types-2.md) | Optional | The type of card for which the terminal accepts store-and-forward payments. You can specify multiple card types. | getSupportedCardTypes(): ?SupportedCardTypes2 | setSupportedCardTypes(?SupportedCardTypes2 supportedCardTypes): void |

## Example

```php
use AdyenLib\Models\Builders\StoreAndForwardBuilder;
use AdyenLib\Models\Builders\MinorUnitsMonetaryValueBuilder;
use AdyenLib\Models\Builders\SupportedCardTypes2Builder;

$storeAndForward = StoreAndForwardBuilder::init()
    ->maxAmount(
        [
            MinorUnitsMonetaryValueBuilder::init()
                ->amount(50)
                ->currencyCode('currencyCode4')
                ->build()
        ]
    )
    ->maxPayments(110)
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

