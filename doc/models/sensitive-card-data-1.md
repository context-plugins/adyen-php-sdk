
# Sensitive Card Data 1

Sensitive information related to the payment card, entered or read by the Sale System.
If structure non empty and unprotected.

## Structure

`SensitiveCardData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pAN` | `?int` | Optional | Primary Account Number.<br><br>**Constraints**: `>= 8`, `<= 28` | getPAN(): ?int | setPAN(?int pAN): void |
| `cardSeqNumb` | `?int` | Optional | Card Sequence Number.<br>If EntryMode is File, Keyed, or Manual.<br><br>**Constraints**: `>= 2`, `<= 3` | getCardSeqNumb(): ?int | setCardSeqNumb(?int cardSeqNumb): void |
| `expiryDate` | `?int` | Optional | Date after which the card cannot be used.<br>If EntryMode is File.<br><br>**Constraints**: `>= 4`, `<= 4` | getExpiryDate(): ?int | setExpiryDate(?int expiryDate): void |
| `trackData` | [`?(TrackData[])`](../../doc/models/track-data.md) | Optional | Magnetic track or magnetic ink characters line.<br>If EntryMode is MagStripe or RFID . | getTrackData(): ?array | setTrackData(?array trackData): void |

## Example

```php
use AdyenLib\Models\Builders\SensitiveCardData1Builder;
use AdyenLib\Models\Builders\TrackDataBuilder;
use AdyenLib\Models\TrackFormat1Enum;

$sensitiveCardData1 = SensitiveCardData1Builder::init()
    ->pAN(28)
    ->cardSeqNumb(3)
    ->expiryDate(4)
    ->trackData(
        [
            TrackDataBuilder::init(
                'TrackValue6'
            )
                ->trackNumb(3)
                ->trackFormat(TrackFormat1Enum::JISII)
                ->build(),
            TrackDataBuilder::init(
                'TrackValue6'
            )
                ->trackNumb(3)
                ->trackFormat(TrackFormat1Enum::JISII)
                ->build(),
            TrackDataBuilder::init(
                'TrackValue6'
            )
                ->trackNumb(3)
                ->trackFormat(TrackFormat1Enum::JISII)
                ->build()
        ]
    )
    ->build();
```

