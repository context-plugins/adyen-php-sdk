
# Account Identification

## Structure

`AccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AccountIdentificationBuilder;

$accountIdentification = AccountIdentificationBuilder::init()
    ->type('AccountIdentification')
    ->build();
```

