
# Get Tax Form Response 1

## Structure

`GetTaxFormResponse1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `content` | `string` | Required | The content of the tax form in Base64 format. | getContent(): string | setContent(string content): void |
| `contentType` | [`?string(ContentTypeEnum)`](../../doc/models/content-type-enum.md) | Optional | The content type of the tax form.<br><br>Possible values:<br><br>* **application/pdf** | getContentType(): ?string | setContentType(?string contentType): void |

## Example

```php
use AdyenLib\Models\Builders\GetTaxFormResponse1Builder;
use AdyenLib\Models\ContentTypeEnum;

$getTaxFormResponse1 = GetTaxFormResponse1Builder::init(
    'content8'
)
    ->contentType(ContentTypeEnum::ENUM_APPLICATIONPDF)
    ->build();
```

