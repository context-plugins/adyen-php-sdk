
# Href

## Structure

`Href`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\HrefBuilder;

$href = HrefBuilder::init(
    'https://someUrl'
)->build();
```

