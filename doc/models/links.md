
# Links

## Structure

`Links`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |

## Example

```php
use AdyenLib\Models\Builders\LinksBuilder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$links = LinksBuilder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)->build();
```

