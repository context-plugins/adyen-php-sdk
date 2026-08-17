
# Links 7

Reference to resources connected with the store.

## Structure

`Links7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |

## Example

```php
use AdyenLib\Models\Builders\Links7Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$links7 = Links7Builder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)->build();
```

