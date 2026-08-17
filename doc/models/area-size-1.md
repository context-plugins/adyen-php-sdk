
# Area Size 1

Size of an area. Contain the size of the pad area where the signature is written, given with the maximum abscissa and ordinate values (X and Y). The maximum value is FFFF.

## Structure

`AreaSize1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `x` | `string` | Required | Abscissa of a point coordinates. The hexadecimal value in text of the abscissa of the coordinates of a point. Leading zero can be removed (e.g. 3BC, 0, and 1287). | getX(): string | setX(string x): void |
| `y` | `string` | Required | Ordinate of a point coordinates. The hexadecimal value in text of the ordinate of the coordinates of a point. Leading zero can be removed (e.g. 3BC, 0, and 1287). | getY(): string | setY(string y): void |

## Example

```php
use AdyenLib\Models\Builders\AreaSize1Builder;

$areaSize1 = AreaSize1Builder::init(
    'X4',
    'Y2'
)->build();
```

