
# Screen Dimensions

## Structure

`ScreenDimensions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `height` | `?int` | Optional | - | getHeight(): ?int | setHeight(?int height): void |
| `width` | `?int` | Optional | - | getWidth(): ?int | setWidth(?int width): void |

## Example

```php
use AdyenLib\Models\Builders\ScreenDimensionsBuilder;

$screenDimensions = ScreenDimensionsBuilder::init()
    ->height(252)
    ->width(152)
    ->build();
```

