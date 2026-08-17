
# Transaction Search Response

## Structure

`TransactionSearchResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links21`](../../doc/models/links-21.md) | Optional | Contains links to the next and previous page whenever applicable. | getLinks(): ?Links21 | setLinks(?Links21 links): void |
| `data` | [`?(Transaction[])`](../../doc/models/transaction.md) | Optional | Contains the transactions that match the query parameters. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionSearchResponseBuilder;
use AdyenLib\Models\Builders\Links21Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\TransactionBuilder;
use AdyenLib\Models\Builders\ResourceReference3Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\ResourceReference4Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Status72Enum;
use AdyenLib\Models\Builders\PaymentInstrument21Builder;
use AdyenLib\Models\Builders\TransferView2Builder;
use AdyenLib\Models\Builders\BankCategoryDataBuilder;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type310Enum;

$transactionSearchResponse = TransactionSearchResponseBuilder::init()
    ->links(
        Links21Builder::init()
            ->next(
                LinksElementBuilder::init()
                    ->href('href4')
                    ->build()
            )
            ->prev(
                LinksElementBuilder::init()
                    ->href('href8')
                    ->build()
            )
            ->build()
    )
    ->data(
        [
            TransactionBuilder::init(
                ResourceReference3Builder::init()
                    ->description('description0')
                    ->id('id0')
                    ->reference('reference4')
                    ->build(),
                Amount17Builder::init(
                    'currency2',
                    110
                )->build(),
                ResourceReference4Builder::init()
                    ->description('description2')
                    ->id('id2')
                    ->reference('reference2')
                    ->build(),
                'balancePlatform2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
                'id0',
                Status72Enum::BOOKED,
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->description('description0')
                ->paymentInstrument(
                    PaymentInstrument21Builder::init()
                        ->description('description0')
                        ->id('id0')
                        ->reference('reference6')
                        ->tokenType('tokenType6')
                        ->build()
                )
                ->referenceForBeneficiary('referenceForBeneficiary0')
                ->transfer(
                    TransferView2Builder::init(
                        'reference4'
                    )
                        ->categoryData(
                            BankCategoryDataBuilder::init()
                                ->priority(Priority1Enum::INSTANT)
                                ->type(Type310Enum::BANK)
                                ->build()
                        )
                        ->id('id8')
                        ->build()
                )
                ->build(),
            TransactionBuilder::init(
                ResourceReference3Builder::init()
                    ->description('description0')
                    ->id('id0')
                    ->reference('reference4')
                    ->build(),
                Amount17Builder::init(
                    'currency2',
                    110
                )->build(),
                ResourceReference4Builder::init()
                    ->description('description2')
                    ->id('id2')
                    ->reference('reference2')
                    ->build(),
                'balancePlatform2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
                'id0',
                Status72Enum::BOOKED,
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->description('description0')
                ->paymentInstrument(
                    PaymentInstrument21Builder::init()
                        ->description('description0')
                        ->id('id0')
                        ->reference('reference6')
                        ->tokenType('tokenType6')
                        ->build()
                )
                ->referenceForBeneficiary('referenceForBeneficiary0')
                ->transfer(
                    TransferView2Builder::init(
                        'reference4'
                    )
                        ->categoryData(
                            BankCategoryDataBuilder::init()
                                ->priority(Priority1Enum::INSTANT)
                                ->type(Type310Enum::BANK)
                                ->build()
                        )
                        ->id('id8')
                        ->build()
                )
                ->build(),
            TransactionBuilder::init(
                ResourceReference3Builder::init()
                    ->description('description0')
                    ->id('id0')
                    ->reference('reference4')
                    ->build(),
                Amount17Builder::init(
                    'currency2',
                    110
                )->build(),
                ResourceReference4Builder::init()
                    ->description('description2')
                    ->id('id2')
                    ->reference('reference2')
                    ->build(),
                'balancePlatform2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
                'id0',
                Status72Enum::BOOKED,
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->description('description0')
                ->paymentInstrument(
                    PaymentInstrument21Builder::init()
                        ->description('description0')
                        ->id('id0')
                        ->reference('reference6')
                        ->tokenType('tokenType6')
                        ->build()
                )
                ->referenceForBeneficiary('referenceForBeneficiary0')
                ->transfer(
                    TransferView2Builder::init(
                        'reference4'
                    )
                        ->categoryData(
                            BankCategoryDataBuilder::init()
                                ->priority(Priority1Enum::INSTANT)
                                ->type(Type310Enum::BANK)
                                ->build()
                        )
                        ->id('id8')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

