
# Association

## Structure

`Association`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entityId` | `string` | Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` | getEntityId(): string | setEntityId(string entityId): void |
| `entityType` | [`string(ScaEntityType1Enum)`](../../doc/models/sca-entity-type-1-enum.md) | Required | The type of entity you are associating the device with.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. | getEntityType(): string | setEntityType(string entityType): void |
| `scaDeviceId` | `string` | Required | The unique identifier for the SCA device.<br><br>**Constraints**: *Minimum Length*: `30`, *Maximum Length*: `30` | getScaDeviceId(): string | setScaDeviceId(string scaDeviceId): void |
| `status` | [`string(AssociationStatus1Enum)`](../../doc/models/association-status-1-enum.md) | Required | The status of the association.<br><br>Possible values: **active** or **pendingApproval**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationBuilder;
use AdyenLib\Models\ScaEntityType1Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$association = AssociationBuilder::init(
    'entityId2',
    ScaEntityType1Enum::ACCOUNTHOLDER,
    'BSDR11111111111A1AAA1AAAAA1AA1',
    AssociationStatus1Enum::PENDINGAPPROVAL
)->build();
```

