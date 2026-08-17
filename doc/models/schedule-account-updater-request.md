
# Schedule Account Updater Request

## Structure

`ScheduleAccountUpdaterRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular request. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | Credit card data.<br><br>Optional if `shopperReference` and `selectedRecurringDetailReference` are provided. | getCard(): ?Card | setCard(?Card card): void |
| `merchantAccount` | `string` | Required | Account of the merchant. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `reference` | `string` | Required | A reference that merchants can apply for the call. | getReference(): string | setReference(string reference): void |
| `selectedRecurringDetailReference` | `?string` | Optional | The selected detail recurring reference.<br><br>Optional if `card` is provided. | getSelectedRecurringDetailReference(): ?string | setSelectedRecurringDetailReference(?string selectedRecurringDetailReference): void |
| `shopperReference` | `?string` | Optional | The reference of the shopper that owns the recurring contract.<br><br>Optional if `card` is provided. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\ScheduleAccountUpdaterRequestBuilder;
use AdyenLib\Models\Builders\CardBuilder;

$scheduleAccountUpdaterRequest = ScheduleAccountUpdaterRequestBuilder::init(
    'merchantAccount2',
    'reference6'
)
    ->additionalData(
        [
            'key0' => 'additionalData0'
        ]
    )
    ->card(
        CardBuilder::init()
            ->cvc('cvc0')
            ->expiryMonth('expiryMonth0')
            ->expiryYear('expiryYear0')
            ->holderName('holderName2')
            ->issueNumber('issueNumber8')
            ->build()
    )
    ->selectedRecurringDetailReference('selectedRecurringDetailReference0')
    ->shopperReference('shopperReference8')
    ->build();
```

