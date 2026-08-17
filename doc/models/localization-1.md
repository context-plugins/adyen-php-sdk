
# Localization 1

Settings for localization.

## Structure

`Localization1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `language` | `?string` | Optional | Language of the terminal. | getLanguage(): ?string | setLanguage(?string language): void |
| `secondaryLanguage` | `?string` | Optional | Secondary language of the terminal. | getSecondaryLanguage(): ?string | setSecondaryLanguage(?string secondaryLanguage): void |
| `timezone` | `?string` | Optional | The time zone of the terminal. | getTimezone(): ?string | setTimezone(?string timezone): void |

## Example

```php
use AdyenLib\Models\Builders\Localization1Builder;

$localization1 = Localization1Builder::init()
    ->language('language2')
    ->secondaryLanguage('secondaryLanguage4')
    ->timezone('timezone0')
    ->build();
```

