
# POI Software

Information related to the software of the POI System which manages the Sale to POI protocol. In a session allows identifying the product features of a POI System.

## Structure

`POISoftware`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `manufacturerID` | `string` | Required | Identification of the Manufacturer. Sent in the Login Request (Response) to identify the Sale System (POI System) manufacturer during the session.<br><br>**Constraints**: *Pattern*: `^.+$` | getManufacturerID(): string | setManufacturerID(string manufacturerID): void |
| `applicationName` | `string` | Required | Name of the software product. Sent in the Login Request (Response) to identify the Sale System (POI System) product name during the session.<br><br>**Constraints**: *Pattern*: `^.+$` | getApplicationName(): string | setApplicationName(string applicationName): void |
| `softwareVersion` | `string` | Required | Version of the software product. Sent in the Login Request (Response) to identify the version of the Sale System (POI System) product software during the session.<br><br>**Constraints**: *Pattern*: `^.+$` | getSoftwareVersion(): string | setSoftwareVersion(string softwareVersion): void |
| `certificationCode` | `string` | Required | Certification code of the software which manages the Sale to POI protocol. Sent in the Login Request (Response) to get the certification code of the Sale System (POI System) product software. This code can be a software checksum or any number associated with the software.<br><br>**Constraints**: *Pattern*: `^.+$` | getCertificationCode(): string | setCertificationCode(string certificationCode): void |

## Example

```php
use AdyenLib\Models\Builders\POISoftwareBuilder;

$pOISoftware = POISoftwareBuilder::init(
    'ManufacturerID0',
    'ApplicationName2',
    'SoftwareVersion6',
    'CertificationCode0'
)->build();
```

