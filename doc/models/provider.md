
# Provider

## Structure

`Provider`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logoURL` | `string` | Required | The URL of the organization's or brand's logo. This URL typically points to an image file (e.g., .png, .jpg, .svg) that can be displayed to visually represent the entity.<br><br>**Constraints**: *Minimum Length*: `1` | getLogoURL(): string | setLogoURL(string logoURL): void |
| `name` | `string` | Required | The official or commonly used name of the organization, brand, or entity.<br><br>**Constraints**: *Minimum Length*: `1` | getName(): string | setName(string name): void |

## Example

```php
use AdyenLib\Models\Builders\ProviderBuilder;

$provider = ProviderBuilder::init(
    'logoURL6',
    'name8'
)->build();
```

