
# Update Split Configuration Request

## Structure

`UpdateSplitConfigurationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | Your description for the split configuration.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): string | setDescription(string description): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateSplitConfigurationRequestBuilder;

$updateSplitConfigurationRequest = UpdateSplitConfigurationRequestBuilder::init(
    'description8'
)->build();
```

