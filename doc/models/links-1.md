
# Links 1

References to resources connected with this user.

## Structure

`Links1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |

## Example

```php
use AdyenLib\Models\Builders\Links1Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$links1 = Links1Builder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)->build();
```

