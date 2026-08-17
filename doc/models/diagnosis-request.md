
# Diagnosis Request

It conveys Information related to the target POI for which the diagnosis is requested.
Content of the Diagnosis Request message.

## Structure

`DiagnosisRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pOIID` | `?string` | Optional | Identification of a POI System or a POI Terminal for the Sale to POI protocol.<br>MessageHeader.POIID.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): ?string | setPOIID(?string pOIID): void |
| `hostDiagnosisFlag` | `?bool` | Optional | Indicates if Host Diagnosis are required.<br><br>**Default**: `false` | getHostDiagnosisFlag(): ?bool | setHostDiagnosisFlag(?bool hostDiagnosisFlag): void |
| `acquirerID` | `?(int[])` | Optional | Identification of the Acquirer.<br>Present if requesting the diagnosis of these hosts only. | getAcquirerID(): ?array | setAcquirerID(?array acquirerID): void |

## Example

```php
use AdyenLib\Models\Builders\DiagnosisRequestBuilder;

$diagnosisRequest = DiagnosisRequestBuilder::init()
    ->pOIID('POIID0')
    ->hostDiagnosisFlag(false)
    ->acquirerID(
        [
            110,
            109,
            108
        ]
    )
    ->build();
```

