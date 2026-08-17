
# Capability Settings 2

## Structure

`CapabilitySettings2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountPerIndustry` | [`?array<string,PatchableAmountDTO>`](../../doc/models/patchable-amount-dto.md) | Optional | The maximum amount a card holder can spend per industry. | getAmountPerIndustry(): ?array | setAmountPerIndustry(?array amountPerIndustry): void |
| `authorizedCardUsers` | `?bool` | Optional | The number of card holders who can use the card. | getAuthorizedCardUsers(): ?bool | setAuthorizedCardUsers(?bool authorizedCardUsers): void |
| `fundingSource` | [`?(string(FundingSourceEnum)[])`](../../doc/models/funding-source-enum.md) | Optional | The funding source of the card, for example **debit**. | getFundingSource(): ?array | setFundingSource(?array fundingSource): void |
| `interval` | [`?string(IntervalEnum)`](../../doc/models/interval-enum.md) | Optional | The period when the rule conditions apply. | getInterval(): ?string | setInterval(?string interval): void |
| `maxAmount` | [`?PatchableAmountDTO`](../../doc/models/patchable-amount-dto.md) | Optional | The maximum amount a card holder can withdraw per day. | getMaxAmount(): ?PatchableAmountDTO | setMaxAmount(?PatchableAmountDTO maxAmount): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilitySettings2Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;

$capabilitySettings2 = CapabilitySettings2Builder::init()
    ->amountPerIndustry(
        [
            'key0' => PatchableAmountDTOBuilder::init()
                ->currency('currency8')
                ->value(56)
                ->build(),
            'key1' => PatchableAmountDTOBuilder::init()
                ->currency('currency8')
                ->value(56)
                ->build()
        ]
    )
    ->authorizedCardUsers(false)
    ->fundingSource(
        [
            FundingSourceEnum::CREDIT,
            FundingSourceEnum::PREPAID,
            FundingSourceEnum::DEBIT
        ]
    )
    ->interval(IntervalEnum::DAILY)
    ->maxAmount(
        PatchableAmountDTOBuilder::init()
            ->currency('currency4')
            ->value(160)
            ->build()
    )
    ->build();
```

