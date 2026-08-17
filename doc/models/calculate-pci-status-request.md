
# Calculate Pci Status Request

## Structure

`CalculatePciStatusRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalSalesChannels` | [`?(string(AdditionalSalesChannelEnum)[])`](../../doc/models/additional-sales-channel-enum.md) | Optional | An array of additional sales channels to generate PCI questionnaires. Include the relevant sales channels if you need your user to sign PCI questionnaires. Not required if you [create stores](https://docs.adyen.com/platforms) and [add payment methods](https://docs.adyen.com/adyen-for-platforms-model) before you generate the questionnaires.<br><br>Possible values:<br><br>* **eCommerce**<br>* **pos**<br>* **ecomMoto**<br>* **posMoto** | getAdditionalSalesChannels(): ?array | setAdditionalSalesChannels(?array additionalSalesChannels): void |

## Example

```php
use AdyenLib\Models\Builders\CalculatePciStatusRequestBuilder;
use AdyenLib\Models\AdditionalSalesChannelEnum;

$calculatePciStatusRequest = CalculatePciStatusRequestBuilder::init()
    ->additionalSalesChannels(
        [
            AdditionalSalesChannelEnum::POS,
            AdditionalSalesChannelEnum::POSMOTO
        ]
    )
    ->build();
```

