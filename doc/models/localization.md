
# Localization

## Structure

`Localization`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `language` | `?string` | Optional | Language of the terminal. | getLanguage(): ?string | setLanguage(?string language): void |
| `secondaryLanguage` | `?string` | Optional | Secondary language of the terminal. | getSecondaryLanguage(): ?string | setSecondaryLanguage(?string secondaryLanguage): void |
| `timezone` | `?string` | Optional | The time zone of the terminal. | getTimezone(): ?string | setTimezone(?string timezone): void |

## Example

```php
use AdyenLib\Models\Builders\LocalizationBuilder;

$localization = LocalizationBuilder::init()
    ->language('language0')
    ->secondaryLanguage('secondaryLanguage6')
    ->timezone('timezone8')
    ->build();
```

