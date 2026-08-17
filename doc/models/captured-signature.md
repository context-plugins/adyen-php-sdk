
# Captured Signature

## Structure

`CapturedSignature`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `areaSize` | [`?AreaSize1`](../../doc/models/area-size-1.md) | Optional | Size of an area. Contain the size of the pad area where the signature is written, given with the maximum abscissa and ordinate values (X and Y). The maximum value is FFFF. | getAreaSize(): ?AreaSize1 | setAreaSize(?AreaSize1 areaSize): void |
| `signaturePoint` | [`?(Point[])`](../../doc/models/point.md) | Optional | Coordinates of a point where the pen changes direction or lift. Contain the Coordinates of a point of the written signature where the pen changes direction or lift where (X and Y). When the signer lifts the pen, both X and Y have the value FFFF. | getSignaturePoint(): ?array | setSignaturePoint(?array signaturePoint): void |

## Example

```php
use AdyenLib\Models\Builders\CapturedSignatureBuilder;
use AdyenLib\Models\Builders\AreaSize1Builder;
use AdyenLib\Models\Builders\PointBuilder;

$capturedSignature = CapturedSignatureBuilder::init()
    ->areaSize(
        AreaSize1Builder::init(
            'X4',
            'Y8'
        )->build()
    )
    ->signaturePoint(
        [
            PointBuilder::init(
                'X0',
                'Y6'
            )->build(),
            PointBuilder::init(
                'X0',
                'Y6'
            )->build(),
            PointBuilder::init(
                'X0',
                'Y6'
            )->build()
        ]
    )->build();
```

