
# Href 1

The URL to where the user must be redirected after a successful payment.

## Structure

`Href1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\Href1Builder;

$href1 = Href1Builder::init(
    'https://someUrl'
)->build();
```

