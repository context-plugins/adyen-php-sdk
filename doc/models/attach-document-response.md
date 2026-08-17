
# Attach Document Response

## Structure

`AttachDocumentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attachmentId` | `?string` | Optional, Read-only | The unique identifier of the attachment. | getAttachmentId(): ?string | setAttachmentId(?string attachmentId): void |

## Example

```php
use AdyenLib\Models\Builders\AttachDocumentResponseBuilder;

$attachDocumentResponse = AttachDocumentResponseBuilder::init()->build();
```

