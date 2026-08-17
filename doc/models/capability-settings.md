
# Capability Settings

## Structure

`CapabilitySettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountPerIndustry` | [`?array<string,Amount17>`](../../doc/models/amount-17.md) | Optional | - | getAmountPerIndustry(): ?array | setAmountPerIndustry(?array amountPerIndustry): void |
| `authorizedCardUsers` | `?bool` | Optional | - | getAuthorizedCardUsers(): ?bool | setAuthorizedCardUsers(?bool authorizedCardUsers): void |
| `fundingSource` | [`?(string(FundingSourceEnum)[])`](../../doc/models/funding-source-enum.md) | Optional | - | getFundingSource(): ?array | setFundingSource(?array fundingSource): void |
| `interval` | [`?string(IntervalEnum)`](../../doc/models/interval-enum.md) | Optional | - | getInterval(): ?string | setInterval(?string interval): void |
| `maxAmount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getMaxAmount(): ?Amount17 | setMaxAmount(?Amount17 maxAmount): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilitySettingsBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;

$capabilitySettings = CapabilitySettingsBuilder::init()
    ->amountPerIndustry(
        [
            'key0' => Amount17Builder::init(
                'currency8',
                56
            )->build(),
            'key1' => Amount17Builder::init(
                'currency8',
                56
            )->build()
        ]
    )
    ->authorizedCardUsers(false)
    ->fundingSource(
        [
            FundingSourceEnum::DEBIT
        ]
    )
    ->interval(IntervalEnum::WEEKLY)
    ->maxAmount(
        Amount17Builder::init(
            'currency4',
            160
        )->build()
    )->build();
```

