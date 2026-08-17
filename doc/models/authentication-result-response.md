
# Authentication Result Response

## Structure

`AuthenticationResultResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `threeDS1Result` | [`?ThreeDS1Result2`](../../doc/models/three-ds-1-result-2.md) | Optional | The result of the 3D Secure authentication. | getThreeDS1Result(): ?ThreeDS1Result2 | setThreeDS1Result(?ThreeDS1Result2 threeDS1Result): void |
| `threeDS2Result` | [`?ThreeDS2Result`](../../doc/models/three-ds-2-result.md) | Optional | The result of the 3D Secure 2 authentication. | getThreeDS2Result(): ?ThreeDS2Result | setThreeDS2Result(?ThreeDS2Result threeDS2Result): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationResultResponseBuilder;
use AdyenLib\Models\Builders\ThreeDS1Result2Builder;
use AdyenLib\Models\Builders\ThreeDS2ResultBuilder;
use AdyenLib\Models\ChallengeCancelEnum;

$authenticationResultResponse = AuthenticationResultResponseBuilder::init()
    ->threeDS1Result(
        ThreeDS1Result2Builder::init()
            ->cavv('cavv2')
            ->cavvAlgorithm('cavvAlgorithm8')
            ->eci('eci6')
            ->threeDAuthenticatedResponse('threeDAuthenticatedResponse8')
            ->threeDOfferedResponse('threeDOfferedResponse2')
            ->build()
    )
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

