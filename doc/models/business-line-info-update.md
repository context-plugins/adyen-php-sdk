
# Business Line Info Update

## Structure

`BusinessLineInfoUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `industryCode` | `?string` | Optional | A code that represents the industry of your legal entity. For example, **4431A** for computer software stores. | getIndustryCode(): ?string | setIndustryCode(?string industryCode): void |
| `industryCodeDescription` | `?string` | Optional, Read-only | The description of the industry code. | getIndustryCodeDescription(): ?string | setIndustryCodeDescription(?string industryCodeDescription): void |
| `salesChannels` | `?(string[])` | Optional | A list of channels where goods or services are sold.<br><br>Possible values: **pos**, **posMoto**, **eCommerce**, **ecomMoto**, **payByLink**.<br><br>Required only in combination with the `service` **paymentProcessing**. | getSalesChannels(): ?array | setSalesChannels(?array salesChannels): void |
| `sourceOfFunds` | [`?SourceOfFunds11`](../../doc/models/source-of-funds-11.md) | Optional | Contains information about the source of your user's funds. Required only if the `service` is **banking** or **issuing**. | getSourceOfFunds(): ?SourceOfFunds11 | setSourceOfFunds(?SourceOfFunds11 sourceOfFunds): void |
| `webData` | [`?(WebData[])`](../../doc/models/web-data.md) | Optional | List of website URLs where your user's goods or services are sold. When this is required for a service but your user does not have an online presence, provide the reason in the `webDataExemption` object. | getWebData(): ?array | setWebData(?array webData): void |
| `webDataExemption` | [`?WebDataExemption1`](../../doc/models/web-data-exemption-1.md) | Optional | The reason why the web data is not provided. | getWebDataExemption(): ?WebDataExemption1 | setWebDataExemption(?WebDataExemption1 webDataExemption): void |

## Example

```php
use AdyenLib\Models\Builders\BusinessLineInfoUpdateBuilder;
use AdyenLib\Models\Builders\SourceOfFunds11Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\WebDataBuilder;

$businessLineInfoUpdate = BusinessLineInfoUpdateBuilder::init()
    ->industryCode('industryCode0')
    ->salesChannels(
        [
            'salesChannels2'
        ]
    )
    ->sourceOfFunds(
        SourceOfFunds11Builder::init(
            false
        )
            ->amount(
                PatchableAmountDTOBuilder::init()
                    ->currency('currency2')
                    ->value(110)
                    ->build()
            )
            ->assetMonthsHeld(46)
            ->cryptocurrencyExchange('cryptocurrencyExchange2')
            ->dateOfFundsReceived(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->dateOfSourceEvent(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->build()
    )
    ->webData(
        [
            WebDataBuilder::init()
                ->webAddress('webAddress4')
                ->build()
        ]
    )
    ->build();
```

