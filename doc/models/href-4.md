
# Href 4

A short-lived URL that redirects the user to the iDEAL page that is required for authentication.

## Structure

`Href4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\Href4Builder;

$href4 = Href4Builder::init(
    'https://someUrl'
)->build();
```

