
# Reprocess Android App Response

## Structure

`ReprocessAndroidAppResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `?string` | Optional | The result of the reprocess. | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
use AdyenLib\Models\Builders\ReprocessAndroidAppResponseBuilder;

$reprocessAndroidAppResponse = ReprocessAndroidAppResponseBuilder::init()
    ->message('Message6')
    ->build();
```

