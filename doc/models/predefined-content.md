
# Predefined Content

Reference of a predefined message to display or print.
It conveys information related to the predefined message.

## Structure

`PredefinedContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `referenceID` | `string` | Required | Identification of a predefined message to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getReferenceID(): string | setReferenceID(string referenceID): void |
| `language` | `?string` | Optional | Identification of a language.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getLanguage(): ?string | setLanguage(?string language): void |

## Example

```php
use AdyenLib\Models\Builders\PredefinedContentBuilder;

$predefinedContent = PredefinedContentBuilder::init(
    'ReferenceID2'
)
    ->language('Language0')
    ->build();
```

