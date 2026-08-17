
# Point

## Structure

`Point`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `x` | `string` | Required | The hexadecimal value of the coordinates of a point on the abscissa. | getX(): string | setX(string x): void |
| `y` | `string` | Required | The hexadecimal value of the coordinates of a point on the ordinate. | getY(): string | setY(string y): void |

## Example

```php
use AdyenLib\Models\Builders\PointBuilder;

$point = PointBuilder::init(
    'X6',
    'Y0'
)->build();
```

