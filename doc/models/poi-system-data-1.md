
# POI System Data 1

Information related to the POI System.
Returned if the response result is Success.

## Structure

`POISystemData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateTime` | `DateTime` | Required | Date and Time. In the response, the POI System gives its date and time to the Sale System. | getDateTime(): \DateTime | setDateTime(\DateTime dateTime): void |
| `pOISoftware` | [`POISoftware`](../../doc/models/poi-software.md) | Required | Information related to the software of the POI System which manages the Sale to POI protocol. In a session allows identifying the product features of a POI System. | getPOISoftware(): POISoftware | setPOISoftware(POISoftware pOISoftware): void |
| `pOIStatus` | [`?POIStatus`](../../doc/models/poi-status.md) | Optional | Indicate the availability of the POI Terminal components. The data element is absent if the component is not part of the POI Terminal.<br>State of a POI Terminal. | getPOIStatus(): ?POIStatus | setPOIStatus(?POIStatus pOIStatus): void |

## Example

```php
use AdyenLib\Models\Builders\POISystemData1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\POISoftwareBuilder;
use AdyenLib\Models\Builders\POIStatusBuilder;
use AdyenLib\Models\GlobalStatus1Enum;
use AdyenLib\Models\PrinterStatus1Enum;

$pOISystemData1 = POISystemData1Builder::init(
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

