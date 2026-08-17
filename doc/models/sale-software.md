
# Sale Software

Information related to the software of the Sale System which manages the NEXO Sale to POI protocol.

## Structure

`SaleSoftware`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `manufacturerID` | `string` | Required | Identification of the Manufacturer.<br><br>**Constraints**: *Pattern*: `^.+$` | getManufacturerID(): string | setManufacturerID(string manufacturerID): void |
| `applicationName` | `string` | Required | Name of the software product.<br><br>**Constraints**: *Pattern*: `^.+$` | getApplicationName(): string | setApplicationName(string applicationName): void |
| `softwareVersion` | `string` | Required | Version of the software product.<br><br>**Constraints**: *Pattern*: `^.+$` | getSoftwareVersion(): string | setSoftwareVersion(string softwareVersion): void |
| `certificationCode` | `string` | Required | Certification code of the software which manages the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getCertificationCode(): string | setCertificationCode(string certificationCode): void |

## Example

```php
use AdyenLib\Models\Builders\SaleSoftwareBuilder;

$saleSoftware = SaleSoftwareBuilder::init(
    'ManufacturerID2',
    'ApplicationName0',
    'SoftwareVersion8',
    'CertificationCode2'
)->build();
```

