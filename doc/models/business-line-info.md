
# Business Line Info

## Structure

`BusinessLineInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `industryCode` | `string` | Required | A code that represents the industry of the legal entity for [marketplaces](https://docs.adyen.com/marketplaces/verification-requirements/reference-additional-products/#list-industry-codes) or [platforms](https://docs.adyen.com/platforms/verification-requirements/reference-additional-products/#list-industry-codes). For example, **4431A** for computer software stores. | getIndustryCode(): string | setIndustryCode(string industryCode): void |
| `industryCodeDescription` | `?string` | Optional, Read-only | The description of the industry code. | getIndustryCodeDescription(): ?string | setIndustryCodeDescription(?string industryCodeDescription): void |
| `legalEntityId` | `string` | Required | Unique identifier of the [legal entity](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities__resParam_id) that owns the business line. | getLegalEntityId(): string | setLegalEntityId(string legalEntityId): void |
| `salesChannels` | `?(string[])` | Optional | A list of channels where goods or services are sold.<br><br>Possible values: **pos**, **posMoto**, **eCommerce**, **ecomMoto**, **payByLink**.<br><br>Required only in combination with the `service` **paymentProcessing**. | getSalesChannels(): ?array | setSalesChannels(?array salesChannels): void |
| `service` | [`string(ServiceEnum)`](../../doc/models/service-enum.md) | Required | The service for which you are creating the business line.<br><br>Possible values:<br><br>* **paymentProcessing**<br>* **issuing**<br>* **banking** | getService(): string | setService(string service): void |
| `sourceOfFunds` | [`?SourceOfFunds11`](../../doc/models/source-of-funds-11.md) | Optional | Contains information about the source of your user's funds. Required only if the `service` is **banking** or **issuing**. | getSourceOfFunds(): ?SourceOfFunds11 | setSourceOfFunds(?SourceOfFunds11 sourceOfFunds): void |
| `webData` | [`?(WebData[])`](../../doc/models/web-data.md) | Optional | List of website URLs where your user's goods or services are sold. When this is required for a service but your user does not have an online presence, provide the reason in the `webDataExemption` object. | getWebData(): ?array | setWebData(?array webData): void |
| `webDataExemption` | [`?WebDataExemption1`](../../doc/models/web-data-exemption-1.md) | Optional | The reason why the web data is not provided. | getWebDataExemption(): ?WebDataExemption1 | setWebDataExemption(?WebDataExemption1 webDataExemption): void |

## Example

```php
use AdyenLib\Models\Builders\BusinessLineInfoBuilder;
use AdyenLib\Models\ServiceEnum;
use AdyenLib\Models\Builders\SourceOfFunds11Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\WebDataBuilder;
use AdyenLib\Models\Builders\WebDataExemption1Builder;
use AdyenLib\Models\Reason3Enum;

$businessLineInfo = BusinessLineInfoBuilder::init(
    'industryCode0',
    'legalEntityId4',
    ServiceEnum::ISSUING
)
    ->salesChannels(
        [
            'salesChannels2',
            'salesChannels3'
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
                ->build(),
            WebDataBuilder::init()
                ->webAddress('webAddress4')
                ->build(),
            WebDataBuilder::init()
                ->webAddress('webAddress4')
                ->build()
        ]
    )
    ->webDataExemption(
        WebDataExemption1Builder::init()
            ->reason(Reason3Enum::NOONLINEPRESENCE)
            ->build()
    )
    ->build();
```

