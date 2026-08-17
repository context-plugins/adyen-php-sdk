
# Diagnosis Response 2

Content of the Diagnosis Response message.

## Structure

`DiagnosisResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `pOIStatus` | [`?POIStatus1`](../../doc/models/poi-status-1.md) | Optional | State of a POI Terminal.<br>If `Response.Result` is Success. | getPOIStatus(): ?POIStatus1 | setPOIStatus(?POIStatus1 pOIStatus): void |
| `hostStatus` | [`?(HostStatus[])`](../../doc/models/host-status.md) | Optional | State of a Host. | getHostStatus(): ?array | setHostStatus(?array hostStatus): void |

## Example

```php
use AdyenLib\Models\Builders\DiagnosisResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\POIStatus1Builder;
use AdyenLib\Models\GlobalStatus1Enum;
use AdyenLib\Models\PrinterStatus1Enum;
use AdyenLib\Models\Builders\HostStatusBuilder;

$diagnosisResponse2 = DiagnosisResponse2Builder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)
    ->pOIStatus(
        POIStatus1Builder::init(
            GlobalStatus1Enum::MAINTENANCE
        )
            ->securityOKFlag(false)
            ->pEDOKFlag(false)
            ->cardReaderOKFlag(false)
            ->printerStatus(PrinterStatus1Enum::PAPERLOW)
            ->communicationOKFlag(false)
            ->build()
    )
    ->hostStatus(
        [
            HostStatusBuilder::init(
                120
            )
                ->isReachableFlag(false)
                ->build(),
            HostStatusBuilder::init(
                120
            )
                ->isReachableFlag(false)
                ->build(),
            HostStatusBuilder::init(
                120
            )
                ->isReachableFlag(false)
                ->build()
        ]
    )
    ->build();
```

