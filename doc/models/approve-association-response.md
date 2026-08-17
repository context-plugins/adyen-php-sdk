
# Approve Association Response

## Structure

`ApproveAssociationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scaAssociations` | [`Association[]`](../../doc/models/association.md) | Required | The list of associations.<br><br>**Constraints**: *Minimum Items*: `1` | getScaAssociations(): array | setScaAssociations(array scaAssociations): void |

## Example

```php
use AdyenLib\Models\Builders\ApproveAssociationResponseBuilder;
use AdyenLib\Models\Builders\AssociationBuilder;
use AdyenLib\Models\ScaEntityType1Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$approveAssociationResponse = ApproveAssociationResponseBuilder::init(
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

