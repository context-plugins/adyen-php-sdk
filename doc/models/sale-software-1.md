
# Sale Software 1

Information related to the software of the Sale System which manages the Sale to POI protocol.

## Structure

`SaleSoftware1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `manufacturerID` | `string` | Required | Identification of the Manufacturer.<br><br>**Constraints**: *Pattern*: `^.+$` | getManufacturerID(): string | setManufacturerID(string manufacturerID): void |
| `applicationName` | `string` | Required | Name of the software product.<br><br>**Constraints**: *Pattern*: `^.+$` | getApplicationName(): string | setApplicationName(string applicationName): void |
| `softwareVersion` | `string` | Required | Version of the software product.<br><br>**Constraints**: *Pattern*: `^.+$` | getSoftwareVersion(): string | setSoftwareVersion(string softwareVersion): void |
| `certificationCode` | `string` | Required | Certification code of the software which manages the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getCertificationCode(): string | setCertificationCode(string certificationCode): void |

## Example

```php
use AdyenLib\Models\Builders\SaleSoftware1Builder;

$saleSoftware1 = SaleSoftware1Builder::init(
    'ManufacturerID0',
    'ApplicationName2',
    'SoftwareVersion6',
    'CertificationCode0'
)->build();
```

