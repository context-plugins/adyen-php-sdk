
# Three DS Availability Request

## Structure

`ThreeDSAvailabilityRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular request.<br><br>The `additionalData` object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `brands` | `?(string[])` | Optional | List of brands. | getBrands(): ?array | setBrands(?array brands): void |
| `cardNumber` | `?string` | Optional | Card number or BIN. | getCardNumber(): ?string | setCardNumber(?string cardNumber): void |
| `merchantAccount` | `string` | Required | The merchant account identifier. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `recurringDetailReference` | `?string` | Optional | A recurring detail reference corresponding to a card. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `shopperReference` | `?string` | Optional | The shopper's reference to uniquely identify this shopper (e.g. user ID or account ID). | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSAvailabilityRequestBuilder;

$threeDSAvailabilityRequest = ThreeDSAvailabilityRequestBuilder::init(
    'merchantAccount6'
)
    ->additionalData(
        [
            'key0' => 'additionalData4'
        ]
    )
    ->brands(
        [
            'brands5',
            'brands6'
        ]
    )
    ->cardNumber('cardNumber0')
    ->recurringDetailReference('recurringDetailReference4')
    ->shopperReference('shopperReference2')
    ->build();
```

