
# Track Data

Magnetic track or magnetic ink characters line.
ISO 7813 - ISO 4909.
Generic data structure for a card track, used when the magstripe card reader is located on the Sale Terminal, or for magstripe Card Reader device request. The data structure is also used to store the line at the bottom of a bank check.

## Structure

`TrackData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `trackNumb` | `?int` | Optional | Card track number.<br><br>**Default**: `2`<br><br>**Constraints**: `>= 1`, `<= 3` | getTrackNumb(): ?int | setTrackNumb(?int trackNumb): void |
| `trackFormat` | [`?string(TrackFormat1Enum)`](../../doc/models/track-format-1-enum.md) | Optional | Card track format.<br>Possible values:<br><br>* **AAMVA**<br>* **ISO** | getTrackFormat(): ?string | setTrackFormat(?string trackFormat): void |
| `trackValue` | `string` | Required | Card track content.<br><br>**Constraints**: *Pattern*: `^.{1,104}$` | getTrackValue(): string | setTrackValue(string trackValue): void |

## Example

```php
use AdyenLib\Models\Builders\TrackDataBuilder;
use AdyenLib\Models\TrackFormat1Enum;

$trackData = TrackDataBuilder::init(
    'TrackValue0'
)
    ->trackNumb(2)
    ->trackFormat(TrackFormat1Enum::JISII)
    ->build();
```

