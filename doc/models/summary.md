
# Summary

## Structure

`Summary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalEntityId` | `string` | Required | The unique identifier of the legal entity. | getLegalEntityId(): string | setLegalEntityId(string legalEntityId): void |
| `taxYears` | `int[]` | Required | The tax years for which the legal entity has a tax form. | getTaxYears(): array | setTaxYears(array taxYears): void |

## Example

```php
use AdyenLib\Models\Builders\SummaryBuilder;

$summary = SummaryBuilder::init(
    'legalEntityId2',
    [
        111
    ]
)->build();
```

