
# Interchange Data

## Structure

`InterchangeData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `interchangeAmount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The currency and value of the adjusted interchange fee. | getInterchangeAmount(): ?Amount17 | setInterchangeAmount(?Amount17 interchangeAmount): void |
| `interchangeRateIndicator` | `?string` | Optional | A 3-character alphanumeric code assigned by Visa that identifies the specific interchange reimbursement program a transaction qualified for. The code is assigned based on the card type, entry mode, and security data provided. | getInterchangeRateIndicator(): ?string | setInterchangeRateIndicator(?string interchangeRateIndicator): void |
| `type` | `string` | Required, Constant | The type of events data.<br><br>Possible values:<br><br>- **interchangeData**: information about the interchange fee applied to a transaction.<br><br>**Value**: `'interchangeData'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\InterchangeDataBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$interchangeData = InterchangeDataBuilder::init()
    ->interchangeAmount(
        Amount17Builder::init(
            'currency2',
            62
        )->build()
    )
    ->interchangeRateIndicator('interchangeRateIndicator6')
    ->build();
```

