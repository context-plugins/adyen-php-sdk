
# Issuing Transaction Data

## Structure

`IssuingTransactionData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `captureCycleId` | `?string` | Optional | captureCycleId associated with transfer event. | getCaptureCycleId(): ?string | setCaptureCycleId(?string captureCycleId): void |
| `type` | `string` | Required, Constant | The type of events data.<br><br>Possible values:<br><br>- **issuingTransactionData**: issuing transaction data<br><br>**Value**: `'issuingTransactionData'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\IssuingTransactionDataBuilder;

$issuingTransactionData = IssuingTransactionDataBuilder::init()
    ->captureCycleId('captureCycleId4')
    ->build();
```

