
# Web Data 1

The website and app URL of the legal entity.

## Structure

`WebData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `webAddress` | `?string` | Optional | The URL of the website or the app store URL. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |
| `webAddressId` | `?string` | Optional, Read-only | The unique identifier of the web address. | getWebAddressId(): ?string | setWebAddressId(?string webAddressId): void |

## Example

```php
use AdyenLib\Models\Builders\WebData1Builder;

$webData1 = WebData1Builder::init()
    ->webAddress('webAddress4')
    ->build();
```

