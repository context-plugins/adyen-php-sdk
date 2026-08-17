
# Find Transfers Response

## Structure

`FindTransfersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links21`](../../doc/models/links-21.md) | Optional | Contains links to the next and previous page whenever applicable. | getLinks(): ?Links21 | setLinks(?Links21 links): void |
| `data` | [`?(TransferData[])`](../../doc/models/transfer-data.md) | Optional | Contains the transfers that match the query parameters. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\FindTransfersResponseBuilder;
use AdyenLib\Models\Builders\Links21Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\TransferDataBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Category3Enum;
use AdyenLib\Models\Status51Enum;
use AdyenLib\Models\Builders\ResourceReference5Builder;
use AdyenLib\Models\Builders\ResourceReference1Builder;
use AdyenLib\Models\Builders\BalanceMutationBuilder;
use AdyenLib\Models\Builders\BankCategoryDataBuilder;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type310Enum;

$findTransfersResponse = FindTransfersResponseBuilder::init()
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
            TransferDataBuilder::init(
                Amount17Builder::init(
                    'currency2',
                    110
                )->build(),
                Category3Enum::INTERNAL,
                Status51Enum::CANCELLED
            )
                ->accountHolder(
                    ResourceReference5Builder::init()
                        ->description('description0')
                        ->id('id0')
                        ->reference('reference4')
                        ->build()
                )
                ->balanceAccount(
                    ResourceReference1Builder::init()
                        ->description('description2')
                        ->id('id2')
                        ->reference('reference2')
                        ->build()
                )
                ->balancePlatform('balancePlatform2')
                ->balances(
                    [
                        BalanceMutationBuilder::init()
                            ->balance(224)
                            ->currency('currency0')
                            ->received(214)
                            ->reserved(158)
                            ->build(),
                        BalanceMutationBuilder::init()
                            ->balance(224)
                            ->currency('currency0')
                            ->received(214)
                            ->reserved(158)
                            ->build(),
                        BalanceMutationBuilder::init()
                            ->balance(224)
                            ->currency('currency0')
                            ->received(214)
                            ->reserved(158)
                            ->build()
                    ]
                )
                ->categoryData(
                    BankCategoryDataBuilder::init()
                        ->priority(Priority1Enum::INSTANT)
                        ->type(Type310Enum::BANK)
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

