
# Sound Content

## Structure

`SoundContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `soundFormat` | [`string(SoundFormat1Enum)`](../../doc/models/sound-format-1-enum.md) | Required | Possible values:<br><br>* **MessageRef**<br>* **SoundRef**<br>* **Text** | getSoundFormat(): string | setSoundFormat(string soundFormat): void |
| `language` | `?string` | Optional | **Constraints**: *Pattern*: `^[a-z]{2,2}$` | getLanguage(): ?string | setLanguage(?string language): void |
| `referenceID` | `?string` | Optional | **Constraints**: *Pattern*: `^.+$` | getReferenceID(): ?string | setReferenceID(?string referenceID): void |
| `text` | `?string` | Optional | **Constraints**: *Pattern*: `^.+$` | getText(): ?string | setText(?string text): void |

## Example

```php
use AdyenLib\Models\Builders\SoundContentBuilder;
use AdyenLib\Models\SoundFormat1Enum;

$soundContent = SoundContentBuilder::init(
    SoundFormat1Enum::SOUNDREF
)
    ->language('Language6')
    ->referenceID('ReferenceID6')
    ->text('Text6')
    ->build();
```

