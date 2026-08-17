
# Geographic Coordinates

## Structure

`GeographicCoordinates`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `latitude` | `string` | Required | Angular distance of a location on the earth south or north of the equator.<br><br>**Constraints**: *Pattern*: `^.+$` | getLatitude(): string | setLatitude(string latitude): void |
| `longitude` | `string` | Required | Angular measurement of the distance of a location on the earth east or west of the Greenwich observatory.<br><br>**Constraints**: *Pattern*: `^.+$` | getLongitude(): string | setLongitude(string longitude): void |

## Example

```php
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;

$geographicCoordinates = GeographicCoordinatesBuilder::init(
    'Latitude6',
    'Longitude4'
)->build();
```

