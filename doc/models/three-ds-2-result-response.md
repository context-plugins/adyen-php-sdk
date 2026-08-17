
# Three DS 2 Result Response

## Structure

`ThreeDS2ResultResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `threeDS2Result` | [`?ThreeDS2Result`](../../doc/models/three-ds-2-result.md) | Optional | The result of the 3D Secure 2 authentication. | getThreeDS2Result(): ?ThreeDS2Result | setThreeDS2Result(?ThreeDS2Result threeDS2Result): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDS2ResultResponseBuilder;
use AdyenLib\Models\Builders\ThreeDS2ResultBuilder;
use AdyenLib\Models\ChallengeCancelEnum;

$threeDS2ResultResponse = ThreeDS2ResultResponseBuilder::init()
    ->threeDS2Result(
        ThreeDS2ResultBuilder::init()
            ->authenticationValue('authenticationValue8')
            ->cavvAlgorithm('cavvAlgorithm8')
            ->challengeCancel(ChallengeCancelEnum::ENUM_06)
            ->dsTransID('dsTransID2')
            ->eci('eci6')
            ->build()
    )
    ->build();
```

