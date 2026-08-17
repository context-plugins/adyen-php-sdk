
# Area Size

## Structure

`AreaSize`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `x` | `string` | Required | Abscissa of a point coordinates. The hexadecimal value in text of the abscissa of the coordinates of a point. Leading zero can be removed (e.g. 3BC, 0, and 1287). | getX(): string | setX(string x): void |
| `y` | `string` | Required | Ordinate of a point coordinates. The hexadecimal value in text of the ordinate of the coordinates of a point. Leading zero can be removed (e.g. 3BC, 0, and 1287). | getY(): string | setY(string y): void |

## Example

```php
use AdyenLib\Models\Builders\AreaSizeBuilder;

$areaSize = AreaSizeBuilder::init(
    'X4',
    'Y8'
)->build();
```

