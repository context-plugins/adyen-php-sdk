
# Transfer Limit List Response

## Structure

`TransferLimitListResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferLimits` | [`TransferLimit[]`](../../doc/models/transfer-limit.md) | Required | List of available transfer limits. | getTransferLimits(): array | setTransferLimits(array transferLimits): void |

## Example

```php
use AdyenLib\Models\Builders\TransferLimitListResponseBuilder;
use AdyenLib\Models\Builders\TransferLimitBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\LimitStatusEnum;
use AdyenLib\Models\ScopeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TransferTypeEnum;
use AdyenLib\Models\Builders\ScaInformation1Builder;
use AdyenLib\Models\ScaStatusEnum;
use AdyenLib\Models\ScaExemptionEnum;

$transferLimitListResponse = TransferLimitListResponseBuilder::init(
    [
        TransferLimitBuilder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build(),
            'id8',
            LimitStatusEnum::PENDINGSCA,
            ScopeEnum::PERDAY,
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            TransferTypeEnum::INSTANT
        )
            ->endsAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->reference('reference6')
            ->scaInformation(
                ScaInformation1Builder::init(
                    ScaStatusEnum::PENDING
                )
                    ->exemption(ScaExemptionEnum::NOTREGULATED)
                    ->build()
            )
            ->build()
    ]
)->build();
```

