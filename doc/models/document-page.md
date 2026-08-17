
# Document Page

## Structure

`DocumentPage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pageName` | `?string` | Optional | - | getPageName(): ?string | setPageName(?string pageName): void |
| `pageNumber` | `?int` | Optional | - | getPageNumber(): ?int | setPageNumber(?int pageNumber): void |
| `type` | [`?string(Type91Enum)`](../../doc/models/type-91-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DocumentPageBuilder;
use AdyenLib\Models\Type91Enum;

$documentPage = DocumentPageBuilder::init()
    ->pageName('pageName0')
    ->pageNumber(88)
    ->type(Type91Enum::FRONT)
    ->build();
```

