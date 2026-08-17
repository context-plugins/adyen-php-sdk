
# Get Dynamic Offers Response

## Structure

`GetDynamicOffersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dynamicOffers` | [`DynamicOffer[]`](../../doc/models/dynamic-offer.md) | Required | Contains a list of available dynamic offers for the specified account holder. | getDynamicOffers(): array | setDynamicOffers(array dynamicOffers): void |

## Example

```php
use AdyenLib\Models\Builders\GetDynamicOffersResponseBuilder;
use AdyenLib\Models\Builders\DynamicOfferBuilder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\FinancingType2Enum;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\DynamicOfferRepayment2Builder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;

$getDynamicOffersResponse = GetDynamicOffersResponseBuilder::init(
    [
        DynamicOfferBuilder::init(
            'accountHolderId4',
            ContractTypeEnum::CASHADVANCE,
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            FinancingType2Enum::HARDWAREFINANCING,
            'id2',
            Amount17Builder::init(
                'currency0',
                190
            )->build(),
            Amount17Builder::init(
                'currency2',
                96
            )->build(),
            DynamicOfferRepayment2Builder::init(
                RepaymentTermBuilder::init(
                    248
                )
                    ->maximumDays(24)
                    ->build()
            )->build(),
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    ]
)->build();
```

