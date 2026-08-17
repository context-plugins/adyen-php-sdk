
# Grant Offers

## Structure

`GrantOffers`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `grantOffers` | [`GrantOffer[]`](../../doc/models/grant-offer.md) | Required | A list of available grant offers. | getGrantOffers(): array | setGrantOffers(array grantOffers): void |

## Example

```php
use AdyenLib\Models\Builders\GrantOffersBuilder;
use AdyenLib\Models\Builders\GrantOfferBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\Fee1Builder;

$grantOffers = GrantOffersBuilder::init(
    [
        GrantOfferBuilder::init(
            'accountHolderId0'
        )
            ->amount(
                Amount17Builder::init(
                    'currency2',
                    110
                )->build()
            )
            ->contractType(ContractTypeEnum::CASHADVANCE)
            ->expiresAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->fee(
                Fee1Builder::init(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build()
            )
            ->id('id8')
            ->build()
    ]
)->build();
```

