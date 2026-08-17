
# Provider 2

Metadata about the selected provider, including the name and company logo. You can use this information to inform the user about the provider they will be redirected to when they select the link.

## Structure

`Provider2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logoURL` | `string` | Required | The URL of the organization's or brand's logo. This URL typically points to an image file (e.g., .png, .jpg, .svg) that can be displayed to visually represent the entity.<br><br>**Constraints**: *Minimum Length*: `1` | getLogoURL(): string | setLogoURL(string logoURL): void |
| `name` | `string` | Required | The official or commonly used name of the organization, brand, or entity.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): string | setName(string name): void |

## Example

```php
use AdyenLib\Models\Builders\Provider2Builder;

$provider2 = Provider2Builder::init(
    'logoURL6',
    'name8'
)->build();
```

