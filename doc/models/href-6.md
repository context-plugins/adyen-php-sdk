
# Href 6

The URL to where the user must be redirected after a payment has been canceled.

## Structure

`Href6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\Href6Builder;

$href6 = Href6Builder::init(
    'https://someUrl'
)->build();
```

