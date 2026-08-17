
# Approve Association Request

## Structure

`ApproveAssociationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entityId` | `string` | Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` | getEntityId(): string | setEntityId(string entityId): void |
| `entityType` | [`string(ScaEntityType2Enum)`](../../doc/models/sca-entity-type-2-enum.md) | Required | The type of the entity.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. | getEntityType(): string | setEntityType(string entityType): void |
| `scaDeviceIds` | `string[]` | Required | List of device ids associated to the entity that will be approved.<br><br>**Constraints**: *Minimum Items*: `0`, *Maximum Items*: `5`, *Minimum Length*: `30`, *Maximum Length*: `30` | getScaDeviceIds(): array | setScaDeviceIds(array scaDeviceIds): void |
| `status` | [`string(AssociationStatus1Enum)`](../../doc/models/association-status-1-enum.md) | Required | The status of the association.<br><br>Possible values: **active** or **pendingApproval**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\ApproveAssociationRequestBuilder;
use AdyenLib\Models\ScaEntityType2Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$approveAssociationRequest = ApproveAssociationRequestBuilder::init(
    'entityId8',
    ScaEntityType2Enum::PAYMENTINSTRUMENT,
    [
        'scaDeviceIds4',
        'scaDeviceIds5',
        'scaDeviceIds6'
    ],
    AssociationStatus1Enum::PENDINGAPPROVAL
)->build();
```

