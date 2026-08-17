
# UTM Coordinates

## Structure

`UTMCoordinates`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `uTMZone` | `string` | Required | UTM grid zone combination of the longitude zone (1 to 60) and the latitude band (C to X, excluding I and O).<br><br>**Constraints**: *Pattern*: `^.+$` | getUTMZone(): string | setUTMZone(string uTMZone): void |
| `uTMEastward` | `string` | Required | X-coordinate of the Universal Transverse Mercator coordinate system.<br><br>**Constraints**: *Pattern*: `^.+$` | getUTMEastward(): string | setUTMEastward(string uTMEastward): void |
| `uTMNorthward` | `string` | Required | Y-coordinate of the Universal Transverse Mercator coordinate system.<br><br>**Constraints**: *Pattern*: `^.+$` | getUTMNorthward(): string | setUTMNorthward(string uTMNorthward): void |

## Example

```php
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;

$uTMCoordinates = UTMCoordinatesBuilder::init(
    'UTMZone2',
    'UTMEastward4',
    'UTMNorthward4'
)->build();
```

