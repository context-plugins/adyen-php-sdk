
# Association Listing

## Structure

`AssociationListing`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `DateTime` | Required | The date and time when the association was created. | getCreatedAt(): \DateTime | setCreatedAt(\DateTime createdAt): void |
| `entityId` | `string` | Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` | getEntityId(): string | setEntityId(string entityId): void |
| `entityType` | [`string(ScaEntityType2Enum)`](../../doc/models/sca-entity-type-2-enum.md) | Required | The type of the entity.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. | getEntityType(): string | setEntityType(string entityType): void |
| `scaDeviceId` | `string` | Required | The unique identifier of the SCA device.<br><br>**Constraints**: *Minimum Length*: `30`, *Maximum Length*: `30` | getScaDeviceId(): string | setScaDeviceId(string scaDeviceId): void |
| `scaDeviceName` | `?string` | Optional | The human-readable name for the SCA device that was registered.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `64` | getScaDeviceName(): ?string | setScaDeviceName(?string scaDeviceName): void |
| `scaDeviceType` | [`string(ScaDeviceType3Enum)`](../../doc/models/sca-device-type-3-enum.md) | Required | The type of the device. | getScaDeviceType(): string | setScaDeviceType(string scaDeviceType): void |
| `status` | [`string(AssociationStatus1Enum)`](../../doc/models/association-status-1-enum.md) | Required | The status of the association.<br><br>Possible values: **active** or **pendingApproval**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationListingBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ScaEntityType2Enum;
use AdyenLib\Models\ScaDeviceType3Enum;
use AdyenLib\Models\AssociationStatus1Enum;

$associationListing = AssociationListingBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    'entityId8',
    ScaEntityType2Enum::PAYMENTINSTRUMENT,
    'BSDR11111111111A1AAA1AAAAA1AA1',
    ScaDeviceType3Enum::BROWSER,
    AssociationStatus1Enum::PENDINGAPPROVAL
)
    ->scaDeviceName('scaDeviceName0')
    ->build();
```

