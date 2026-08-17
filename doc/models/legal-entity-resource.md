
# Legal Entity Resource

## Structure

`LegalEntityResource`

## Inherits From

[`Resource2`](../../doc/models/resource-2.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legalEntityId` | `string` | Required | The unique identifier of the resource connected to the component.<br>For [Onboarding components](https://docs.adyen.com/platforms/onboard-users/components), this is the legal entity that has a contractual relationship with your platform and owns the [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments). For sole proprietorships, this is the legal entity of the individual owner.<br><br>**Constraints**: *Minimum Length*: `1` | getLegalEntityId(): string | setLegalEntityId(string legalEntityId): void |

## Example

```php
use AdyenLib\Models\Builders\LegalEntityResourceBuilder;

$legalEntityResource = LegalEntityResourceBuilder::init(
    'legalEntityId6'
)
    ->type('legalEntity')
    ->build();
```

