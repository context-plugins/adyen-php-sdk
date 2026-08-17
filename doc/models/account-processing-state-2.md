
# Account Processing State 2

The processing state of the account holder.

## Structure

`AccountProcessingState2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disableReason` | `?string` | Optional | The reason why processing has been disabled. | getDisableReason(): ?string | setDisableReason(?string disableReason): void |
| `disabled` | `?bool` | Optional | Indicates whether the processing of payments is allowed. | getDisabled(): ?bool | setDisabled(?bool disabled): void |
| `processedFrom` | [`?Amount`](../../doc/models/amount.md) | Optional | The lower bound of the processing tier (i.e., an account holder must have processed at least this amount of money in order to be placed into this tier). | getProcessedFrom(): ?Amount | setProcessedFrom(?Amount processedFrom): void |
| `processedTo` | [`?Amount`](../../doc/models/amount.md) | Optional | The upper bound of the processing tier (i.e., an account holder must have processed less than this amount of money in order to be placed into this tier). | getProcessedTo(): ?Amount | setProcessedTo(?Amount processedTo): void |
| `tierNumber` | `?int` | Optional | The processing tier that the account holder occupies. | getTierNumber(): ?int | setTierNumber(?int tierNumber): void |

## Example

```php
use AdyenLib\Models\Builders\AccountProcessingState2Builder;
use AdyenLib\Models\Builders\AmountBuilder;

$accountProcessingState2 = AccountProcessingState2Builder::init()
    ->disableReason('disableReason2')
    ->disabled(false)
    ->processedFrom(
        AmountBuilder::init(
            'currency4',
            148
        )->build()
    )
    ->processedTo(
        AmountBuilder::init(
            'currency2',
            54
        )->build()
    )
    ->tierNumber(88)
    ->build();
```

