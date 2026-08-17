
# Remove Association Request

## Structure

`RemoveAssociationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entityId` | `string` | Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` | getEntityId(): string | setEntityId(string entityId): void |
| `entityType` | [`string(ScaEntityType3Enum)`](../../doc/models/sca-entity-type-3-enum.md) | Required | The type of the entity.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. | getEntityType(): string | setEntityType(string entityType): void |
| `scaDeviceIds` | `string[]` | Required | A list of device ids associated with the entity that should be removed.<br><br>**Constraints**: *Minimum Items*: `0`, *Maximum Items*: `5`, *Minimum Length*: `30`, *Maximum Length*: `30` | getScaDeviceIds(): array | setScaDeviceIds(array scaDeviceIds): void |

## Example

```php
use AdyenLib\Models\Builders\RemoveAssociationRequestBuilder;
use AdyenLib\Models\ScaEntityType3Enum;

$removeAssociationRequest = RemoveAssociationRequestBuilder::init(
    'entityId0',
    ScaEntityType3Enum::LEGALENTITY,
    [
        'scaDeviceIds4',
        'scaDeviceIds3'
    ]
)->build();
```

