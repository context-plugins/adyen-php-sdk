
# List Mandates Response

## Structure

`ListMandatesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `link` | [`Link2`](../../doc/models/link-2.md) | Required | Contains links to the next and previous page whenever applicable. | getLink(): Link2 | setLink(Link2 link): void |
| `mandates` | [`Mandate1[]`](../../doc/models/mandate-1.md) | Required | Contains a list of the mandates. | getMandates(): array | setMandates(array mandates): void |

## Example

```php
use AdyenLib\Models\Builders\ListMandatesResponseBuilder;
use AdyenLib\Models\Builders\Link2Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;
use AdyenLib\Models\Builders\Mandate1Builder;
use AdyenLib\Models\Builders\MandateBankAccount2Builder;
use AdyenLib\Models\Builders\MandatePartyIdentification2Builder;
use AdyenLib\Models\Builders\MandateAccountIdentification2Builder;
use AdyenLib\Utils\DateTimeHelper;

$listMandatesResponse = ListMandatesResponseBuilder::init(
    Link2Builder::init()
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
        Mandate1Builder::init()
            ->balanceAccountId('balanceAccountId4')
            ->counterparty(
                MandateBankAccount2Builder::init(
                    MandatePartyIdentification2Builder::init()
                        ->fullName('fullName0')
                        ->build(),
                    MandateAccountIdentification2Builder::init()
                        ->type('MandateAccountIdentification2')
                        ->build()
                )->build()
            )
            ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->id('id4')
            ->paymentInstrumentId('paymentInstrumentId6')
            ->build()
    ]
)->build();
```

