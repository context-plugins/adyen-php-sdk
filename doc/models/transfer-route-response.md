
# Transfer Route Response

## Structure

`TransferRouteResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transferRoutes` | [`?(TransferRoute[])`](../../doc/models/transfer-route.md) | Optional | List of available priorities for a transfer, along with requirements. Use this information to initiate a transfer. | getTransferRoutes(): ?array | setTransferRoutes(?array transferRoutes): void |

## Example

```php
use AdyenLib\Models\Builders\TransferRouteResponseBuilder;
use AdyenLib\Models\Builders\TransferRouteBuilder;
use AdyenLib\Models\Category2Enum;
use AdyenLib\Models\Priority2Enum;
use AdyenLib\Models\Builders\AdditionalBankIdentificationRequirementBuilder;
use AdyenLib\Models\AdditionalBankIdentificationTypeEnum;

$transferRouteResponse = TransferRouteResponseBuilder::init()
    ->transferRoutes(
        [
            TransferRouteBuilder::init()
                ->category(Category2Enum::TOPUP)
                ->country('country4')
                ->currency('currency0')
                ->priority(Priority2Enum::INSTANT)
                ->requirements(
                    [
                        AdditionalBankIdentificationRequirementBuilder::init()
                            ->additionalBankIdentificationType(AdditionalBankIdentificationTypeEnum::GBSORTCODE)
                            ->description('description8')
                            ->build()
                    ]
                )
                ->build(),
            TransferRouteBuilder::init()
                ->category(Category2Enum::TOPUP)
                ->country('country4')
                ->currency('currency0')
                ->priority(Priority2Enum::INSTANT)
                ->requirements(
                    [
                        AdditionalBankIdentificationRequirementBuilder::init()
                            ->additionalBankIdentificationType(AdditionalBankIdentificationTypeEnum::GBSORTCODE)
                            ->description('description8')
                            ->build()
                    ]
                )
                ->build(),
            TransferRouteBuilder::init()
                ->category(Category2Enum::TOPUP)
                ->country('country4')
                ->currency('currency0')
                ->priority(Priority2Enum::INSTANT)
                ->requirements(
                    [
                        AdditionalBankIdentificationRequirementBuilder::init()
                            ->additionalBankIdentificationType(AdditionalBankIdentificationTypeEnum::GBSORTCODE)
                            ->description('description8')
                            ->build()
                    ]
                )
                ->build()
        ]
    )
    ->build();
```

