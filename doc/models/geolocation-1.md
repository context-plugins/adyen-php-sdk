
# Geolocation 1

Geographic location specified by geographic or UTM coordinates.
If data available.

## Structure

`Geolocation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `geographicCoordinates` | [`?GeographicCoordinates`](../../doc/models/geographic-coordinates.md) | Optional | - | getGeographicCoordinates(): ?GeographicCoordinates | setGeographicCoordinates(?GeographicCoordinates geographicCoordinates): void |
| `uTMCoordinates` | [`?UTMCoordinates`](../../doc/models/utm-coordinates.md) | Optional | - | getUTMCoordinates(): ?UTMCoordinates | setUTMCoordinates(?UTMCoordinates uTMCoordinates): void |

## Example

```php
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;

$geolocation1 = Geolocation1Builder::init()
    ->geographicCoordinates(
        GeographicCoordinatesBuilder::init(
            'Latitude4',
            'Longitude2'
        )->build()
    )
    ->uTMCoordinates(
        UTMCoordinatesBuilder::init(
            'UTMZone6',
            'UTMEastward0',
            'UTMNorthward0'
        )->build()
    )->build();
```

