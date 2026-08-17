
# Document Reference

## Structure

`DocumentReference`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `active` | `?bool` | Optional | Identifies whether the document is active and used for checks. | getActive(): ?bool | setActive(?bool active): void |
| `description` | `?string` | Optional | Your description for the document. | getDescription(): ?string | setDescription(?string description): void |
| `fileName` | `?string` | Optional | Document name. | getFileName(): ?string | setFileName(?string fileName): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `modificationDate` | `?DateTime` | Optional | The modification date of the document. | getModificationDate(): ?\DateTime | setModificationDate(?\DateTime modificationDate): void |
| `pages` | [`?(DocumentPage[])`](../../doc/models/document-page.md) | Optional | List of document pages | getPages(): ?array | setPages(?array pages): void |
| `type` | `?string` | Optional | Type of document, used when providing an ID number or uploading a document. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DocumentReferenceBuilder;
use AdyenLib\Utils\DateTimeHelper;

$documentReference = DocumentReferenceBuilder::init()
    ->active(false)
    ->description('description8')
    ->fileName('fileName2')
    ->id('id8')
    ->modificationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

