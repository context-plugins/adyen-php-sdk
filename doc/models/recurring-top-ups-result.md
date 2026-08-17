
# Recurring Top Ups Result

## Structure

`RecurringTopUpsResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `link` | [`Link`](../../doc/models/link.md) | Required | - | getLink(): Link | setLink(Link link): void |
| `recurringTopUps` | [`RecurringTopUp[]`](../../doc/models/recurring-top-up.md) | Required | - | getRecurringTopUps(): array | setRecurringTopUps(array recurringTopUps): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringTopUpsResultBuilder;
use AdyenLib\Models\Builders\LinkBuilder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\RecurringTopUpBuilder;
use AdyenLib\Models\Builders\TopUpCounterparty1Builder;
use AdyenLib\Models\Builders\TopUpAmount1Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\Trigger1Builder;
use AdyenLib\Models\Builders\Schedule21Builder;
use AdyenLib\Models\ScheduleType1Enum;
use AdyenLib\Models\Status6Enum;

$recurringTopUpsResult = RecurringTopUpsResultBuilder::init(
    LinkBuilder::init()
        ->first(
            LinksElementBuilder::init()
                ->href('href2')
                ->build()
        )
        ->last(
            LinksElementBuilder::init()
                ->href('href2')
                ->build()
        )
        ->next(
            LinksElementBuilder::init()
                ->href('href4')
                ->build()
        )
        ->previous(
            LinksElementBuilder::init()
                ->href('href0')
                ->build()
        )
        ->self(
            LinksElementBuilder::init()
                ->href('href0')
                ->build()
        )
        ->build(),
    [
        RecurringTopUpBuilder::init(
            TopUpCounterparty1Builder::init(
                'transferInstrumentId4'
            )->build(),
            'description0',
            '',
            TopUpAmount1Builder::init()
                ->fixed(
                    Amount17Builder::init(
                        'currency0',
                        164
                    )->build()
                )
                ->target(
                    Amount17Builder::init(
                        'currency2',
                        188
                    )->build()
                )->build(),
            Trigger1Builder::init(
                Amount17Builder::init(
                    'currency8',
                    32
                )->build()
            )
                ->schedule(
                    Schedule21Builder::init(
                        ScheduleType1Enum::WEEKDAYS
                    )->build()
                )->build()
        )
            ->referenceForBeneficiary('referenceForBeneficiary0')
            ->status(Status6Enum::ACTIVE)
            ->build()
    ]
)->build();
```

