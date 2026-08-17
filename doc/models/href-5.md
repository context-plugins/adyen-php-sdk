
# Href 5

A short-lived URL that redirects the user to the iDEAL profile registration page.

## Structure

`Href5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\Href5Builder;

$href5 = Href5Builder::init(
    'https://someUrl'
)->build();
```

