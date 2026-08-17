
# Href 3

A short-lived URL that redirects the user to the iDEAL profile management page.

## Structure

`Href3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `string` | Required | The full URL for the redirection. | getHref(): string | setHref(string href): void |

## Example

```php
use AdyenLib\Models\Builders\Href3Builder;

$href3 = Href3Builder::init(
    'https://someUrl'
)->build();
```

