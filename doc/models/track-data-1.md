
# Track Data 1

Magnetic track or magnetic ink characters line.
Mandatory if CheckNumber absent.

## Structure

`TrackData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `trackNumb` | `?int` | Optional | Card track number.<br><br>**Default**: `2`<br><br>**Constraints**: `>= 1`, `<= 3` | getTrackNumb(): ?int | setTrackNumb(?int trackNumb): void |
| `trackFormat` | [`?string(TrackFormat1Enum)`](../../doc/models/track-format-1-enum.md) | Optional | Card track format.<br>Possible values:<br><br>* **AAMVA**<br>* **ISO** | getTrackFormat(): ?string | setTrackFormat(?string trackFormat): void |
| `trackValue` | `string` | Required | Card track content.<br><br>**Constraints**: *Pattern*: `^.{1,104}$` | getTrackValue(): string | setTrackValue(string trackValue): void |

## Example

```php
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\TrackFormat1Enum;

$trackData1 = TrackData1Builder::init(
    'TrackValue2'
)
    ->trackNumb(2)
    ->trackFormat(TrackFormat1Enum::JISII)
    ->build();
```

