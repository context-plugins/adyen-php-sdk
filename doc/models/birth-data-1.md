
# Birth Data 1

The individual's birth information.

## Structure

`BirthData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?string` | Optional | The individual's date of birth, in YYYY-MM-DD format. | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |

## Example

```php
use AdyenLib\Models\Builders\BirthData1Builder;

$birthData1 = BirthData1Builder::init()
    ->dateOfBirth('dateOfBirth8')
    ->build();
```

