
# Predefined Content 1

Reference of a predefined message to display or print.
Mandatory, if `OutputFormat` is MessageRef, not allowed otherwise.

## Structure

`PredefinedContent1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `referenceID` | `string` | Required | Identification of a predefined message to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getReferenceID(): string | setReferenceID(string referenceID): void |
| `language` | `?string` | Optional | Identification of a language.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getLanguage(): ?string | setLanguage(?string language): void |

## Example

```php
use AdyenLib\Models\Builders\PredefinedContent1Builder;

$predefinedContent1 = PredefinedContent1Builder::init(
    'ReferenceID6'
)
    ->language('Language6')
    ->build();
```

