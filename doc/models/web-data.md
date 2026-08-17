
# Web Data

## Structure

`WebData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `webAddress` | `?string` | Optional | The URL of the website or the app store URL. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |
| `webAddressId` | `?string` | Optional, Read-only | The unique identifier of the web address. | getWebAddressId(): ?string | setWebAddressId(?string webAddressId): void |

## Example

```php
use AdyenLib\Models\Builders\WebDataBuilder;

$webData = WebDataBuilder::init()
    ->webAddress('webAddress4')
    ->build();
```

