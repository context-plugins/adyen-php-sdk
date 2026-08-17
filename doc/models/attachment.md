
# Attachment

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `content` | `string` | Required | The document in Base64-encoded string format. | getContent(): string | setContent(string content): void |
| `contentType` | `?string` | Optional | The file format.<br><br>Possible values: **application/pdf**, **image/jpg**, **image/jpeg**, **image/png**. | getContentType(): ?string | setContentType(?string contentType): void |
| `filename` | `?string` | Optional | The name of the file including the file extension. | getFilename(): ?string | setFilename(?string filename): void |
| `pageName` | `?string` | Optional | The name of the file including the file extension. | getPageName(): ?string | setPageName(?string pageName): void |
| `pageType` | `?string` | Optional | Specifies which side of the ID card is uploaded.<br><br>* If the `type` is **driversLicense** or **identityCard**, you must set this to **front** or **back** and include both sides in the same API request.<br><br>* For any other types, when this is omitted, we infer the page number based on the order of attachments. | getPageType(): ?string | setPageType(?string pageType): void |

## Example

```php
use AdyenLib\Models\Builders\AttachmentBuilder;

$attachment = AttachmentBuilder::init(
    'content2'
)
    ->contentType('contentType4')
    ->filename('filename0')
    ->pageName('pageName0')
    ->pageType('pageType6')
    ->build();
```

