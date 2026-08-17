
# Birth Data

## Structure

`BirthData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?string` | Optional | The individual's date of birth, in YYYY-MM-DD format. | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |

## Example

```php
use AdyenLib\Models\Builders\BirthDataBuilder;

$birthData = BirthDataBuilder::init()
    ->dateOfBirth('dateOfBirth8')
    ->build();
```

