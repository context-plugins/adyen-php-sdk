
# Pix Pay by Bank Risk Signals

## Structure

`PixPayByBankRiskSignals`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `confidenceScore` | [`?ConfidenceScore`](../../doc/models/confidence-score.md) | Optional | - | getConfidenceScore(): ?ConfidenceScore | setConfidenceScore(?ConfidenceScore confidenceScore): void |
| `elapsedTimeSinceBoot` | `?int` | Optional | - | getElapsedTimeSinceBoot(): ?int | setElapsedTimeSinceBoot(?int elapsedTimeSinceBoot): void |
| `isRootedDevice` | `?bool` | Optional | - | getIsRootedDevice(): ?bool | setIsRootedDevice(?bool isRootedDevice): void |
| `language` | `?string` | Optional | - | getLanguage(): ?string | setLanguage(?string language): void |
| `osVersion` | `?string` | Optional | **Constraints**: *Maximum Length*: `32` | getOsVersion(): ?string | setOsVersion(?string osVersion): void |
| `screenBrightness` | `?int` | Optional | - | getScreenBrightness(): ?int | setScreenBrightness(?int screenBrightness): void |
| `screenDimensions` | [`?ScreenDimensions`](../../doc/models/screen-dimensions.md) | Optional | - | getScreenDimensions(): ?ScreenDimensions | setScreenDimensions(?ScreenDimensions screenDimensions): void |
| `userTimeZoneOffset` | `?int` | Optional | - | getUserTimeZoneOffset(): ?int | setUserTimeZoneOffset(?int userTimeZoneOffset): void |

## Example

```php
use AdyenLib\Models\Builders\PixPayByBankRiskSignalsBuilder;
use AdyenLib\Models\Builders\ConfidenceScoreBuilder;

$pixPayByBankRiskSignals = PixPayByBankRiskSignalsBuilder::init()
    ->confidenceScore(
        ConfidenceScoreBuilder::init()
            ->errors(
                [
                    'errors9',
                    'errors0',
                    'errors1'
                ]
            )
            ->score(155.44)
            ->build()
    )
    ->elapsedTimeSinceBoot(140)
    ->isRootedDevice(false)
    ->language('language8')
    ->osVersion('osVersion6')
    ->build();
```

