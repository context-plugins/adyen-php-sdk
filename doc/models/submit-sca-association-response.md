
# Submit Sca Association Response

## Structure

`SubmitScaAssociationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scaAssociations` | [`Association[]`](../../doc/models/association.md) | Required | List of associations created to the entities and their statuses.<br><br>**Constraints**: *Minimum Items*: `1` | getScaAssociations(): array | setScaAssociations(array scaAssociations): void |

## Example

```php
use AdyenLib\Models\Builders\SubmitScaAssociationResponseBuilder;
use AdyenLib\Models\Builders\AssociationBuilder;
use AdyenLib\Models\ScaEntityType1Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$submitScaAssociationResponse = SubmitScaAssociationResponseBuilder::init(
    [
        AssociationBuilder::init(
            'entityId6',
            ScaEntityType1Enum::PAYMENTINSTRUMENT,
            'BSDR11111111111A1AAA1AAAAA1AA1',
            AssociationStatus1Enum::PENDINGAPPROVAL
        )->build()
    ]
)->build();
```

