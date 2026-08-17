
# POI System Data

## Structure

`POISystemData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateTime` | `DateTime` | Required | Date and Time. In the response, the POI System gives its date and time to the Sale System. | getDateTime(): \DateTime | setDateTime(\DateTime dateTime): void |
| `pOISoftware` | [`POISoftware`](../../doc/models/poi-software.md) | Required | Information related to the software of the POI System which manages the Sale to POI protocol. In a session allows identifying the product features of a POI System. | getPOISoftware(): POISoftware | setPOISoftware(POISoftware pOISoftware): void |
| `pOIStatus` | [`?POIStatus`](../../doc/models/poi-status.md) | Optional | Indicate the availability of the POI Terminal components. The data element is absent if the component is not part of the POI Terminal.<br>State of a POI Terminal. | getPOIStatus(): ?POIStatus | setPOIStatus(?POIStatus pOIStatus): void |

## Example

```php
use AdyenLib\Models\Builders\POISystemDataBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\POISoftwareBuilder;
use AdyenLib\Models\Builders\POIStatusBuilder;
use AdyenLib\Models\GlobalStatus1Enum;
use AdyenLib\Models\PrinterStatus1Enum;

$pOISystemData = POISystemDataBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    POISoftwareBuilder::init(
        'ManufacturerID4',
        'ApplicationName8',
        'SoftwareVersion0',
        'CertificationCode4'
    )->build()
)
    ->pOIStatus(
        POIStatusBuilder::init(
            GlobalStatus1Enum::MAINTENANCE
        )
            ->securityOKFlag(false)
            ->pEDOKFlag(false)
            ->cardReaderOKFlag(false)
            ->printerStatus(PrinterStatus1Enum::PAPERLOW)
            ->communicationOKFlag(false)
            ->build()
    )
    ->build();
```

