
# Captured Signature 1

Numeric value of a handwritten signature. Contains the value of a handwritten signature, e.g. the signature of a cardholder on the merchant payment receipt. Only one format of the signature is allowed:

* The size of the pad area where the signature is written, given with the maximum abscissa and ordinate values.
* The sequence of coordinates where the pen changes direction or lift.

## Structure

`CapturedSignature1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `areaSize` | [`?AreaSize1`](../../doc/models/area-size-1.md) | Optional | Size of an area. Contain the size of the pad area where the signature is written, given with the maximum abscissa and ordinate values (X and Y). The maximum value is FFFF. | getAreaSize(): ?AreaSize1 | setAreaSize(?AreaSize1 areaSize): void |
| `signaturePoint` | [`?(Point[])`](../../doc/models/point.md) | Optional | Coordinates of a point where the pen changes direction or lift. Contain the Coordinates of a point of the written signature where the pen changes direction or lift where (X and Y). When the signer lifts the pen, both X and Y have the value FFFF. | getSignaturePoint(): ?array | setSignaturePoint(?array signaturePoint): void |

## Example

```php
use AdyenLib\Models\Builders\CapturedSignature1Builder;
use AdyenLib\Models\Builders\AreaSize1Builder;
use AdyenLib\Models\Builders\PointBuilder;

$capturedSignature1 = CapturedSignature1Builder::init()
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

