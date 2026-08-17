
# Cost Estimate Response

## Structure

`CostEstimateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardBin` | [`?CardBin1`](../../doc/models/card-bin-1.md) | Optional | Card BIN details. | getCardBin(): ?CardBin1 | setCardBin(?CardBin1 cardBin): void |
| `costEstimateAmount` | [`?Amount`](../../doc/models/amount.md) | Optional | The estimated cost (scheme fee + interchange) in the settlement currency. If the settlement currency cannot be determined, the fee in EUR is returned. | getCostEstimateAmount(): ?Amount | setCostEstimateAmount(?Amount costEstimateAmount): void |
| `costEstimateReference` | `?string` | Optional | Adyen's 16-character reference associated with the request. | getCostEstimateReference(): ?string | setCostEstimateReference(?string costEstimateReference): void |
| `resultCode` | `?string` | Optional | The result of the cost estimation. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\CostEstimateResponseBuilder;
use AdyenLib\Models\Builders\CardBin1Builder;
use AdyenLib\Models\Builders\AmountBuilder;

$costEstimateResponse = CostEstimateResponseBuilder::init()
    ->cardBin(
        CardBin1Builder::init()
            ->bin('bin6')
            ->commercial(false)
            ->fundingSource('fundingSource0')
            ->fundsAvailability('fundsAvailability0')
            ->issuerBin('issuerBin8')
            ->build()
    )
    ->costEstimateAmount(
        AmountBuilder::init(
            'currency8',
            90
        )->build()
    )
    ->costEstimateReference('costEstimateReference8')
    ->resultCode('resultCode4')
    ->build();
```

