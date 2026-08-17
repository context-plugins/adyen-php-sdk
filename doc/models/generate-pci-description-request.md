
# Generate Pci Description Request

## Structure

`GeneratePciDescriptionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalSalesChannels` | [`?(string(AdditionalSalesChannelEnum)[])`](../../doc/models/additional-sales-channel-enum.md) | Optional | An array of additional sales channels to generate PCI questionnaires. Include the relevant sales channels if you need your user to sign PCI questionnaires. Not required if you [create stores](https://docs.adyen.com/platforms) and [add payment methods](https://docs.adyen.com/adyen-for-platforms-model) before you generate the questionnaires.<br><br>Possible values:<br><br>* **eCommerce**<br>* **pos**<br>* **ecomMoto**<br>* **posMoto** | getAdditionalSalesChannels(): ?array | setAdditionalSalesChannels(?array additionalSalesChannels): void |
| `language` | `?string` | Optional | Sets the language of the PCI questionnaire. Its value is a two-character [ISO 639-1](https://en.wikipedia.org/wiki/ISO_639-1) language code, for example, **en**. | getLanguage(): ?string | setLanguage(?string language): void |

## Example

```php
use AdyenLib\Models\Builders\GeneratePciDescriptionRequestBuilder;
use AdyenLib\Models\AdditionalSalesChannelEnum;

$generatePciDescriptionRequest = GeneratePciDescriptionRequestBuilder::init()
    ->additionalSalesChannels(
        [
            AdditionalSalesChannelEnum::POS,
            AdditionalSalesChannelEnum::POSMOTO,
            AdditionalSalesChannelEnum::ECOMMERCE
        ]
    )
    ->language('language0')
    ->build();
```

