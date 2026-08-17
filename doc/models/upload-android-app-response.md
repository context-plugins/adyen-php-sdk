
# Upload Android App Response

## Structure

`UploadAndroidAppResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the uploaded Android app. | getId(): ?string | setId(?string id): void |

## Example

```php
use AdyenLib\Models\Builders\UploadAndroidAppResponseBuilder;

$uploadAndroidAppResponse = UploadAndroidAppResponseBuilder::init()
    ->id('id2')
    ->build();
```

