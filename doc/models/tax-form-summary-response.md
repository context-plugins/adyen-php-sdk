
# Tax Form Summary Response

## Structure

`TaxFormSummaryResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`Summary[]`](../../doc/models/summary.md) | Required | A list of tax form summaries, where each summary consists of the legal entity and the tax years in which the legal entity has a tax form. | getData(): array | setData(array data): void |

## Example

```php
use AdyenLib\Models\Builders\TaxFormSummaryResponseBuilder;
use AdyenLib\Models\Builders\SummaryBuilder;

$taxFormSummaryResponse = TaxFormSummaryResponseBuilder::init(
    [
        SummaryBuilder::init(
            'legalEntityId6',
            [
                221,
                222,
                223
            ]
        )->build()
    ]
)->build();
```

