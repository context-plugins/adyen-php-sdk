
# Attachment 1

Object that contains the document.

## Structure

`Attachment1`

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
use AdyenLib\Models\Builders\Attachment1Builder;

$attachment1 = Attachment1Builder::init(
    'content6'
)
    ->contentType('contentType8')
    ->filename('filename4')
    ->pageName('pageName4')
    ->pageType('pageType0')
    ->build();
```

