
# Login Response 2

Content of the Login Response message.

## Structure

`LoginResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `pOISystemData` | [`?POISystemData1`](../../doc/models/poi-system-data-1.md) | Optional | Information related to the POI System.<br>Returned if the response result is Success. | getPOISystemData(): ?POISystemData1 | setPOISystemData(?POISystemData1 pOISystemData): void |
| `tokenRequestStatus` | `?bool` | Optional | If token is managed by the POI, the status of the token request. | getTokenRequestStatus(): ?bool | setTokenRequestStatus(?bool tokenRequestStatus): void |

## Example

```php
use AdyenLib\Models\Builders\LoginResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\POISystemData1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\POISoftwareBuilder;
use AdyenLib\Models\Builders\POIStatusBuilder;
use AdyenLib\Models\GlobalStatus1Enum;
use AdyenLib\Models\PrinterStatus1Enum;

$loginResponse2 = LoginResponse2Builder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)
    ->pOISystemData(
        POISystemData1Builder::init(
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
            ->build()
    )
    ->tokenRequestStatus(false)
    ->build();
```

