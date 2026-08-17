
# Notify Shopper Request

## Structure

`NotifyShopperRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount of the upcoming payment. | getAmount(): Amount | setAmount(Amount amount): void |
| `billingDate` | `?string` | Optional | Date on which the subscription amount will be debited from the shopper. In YYYY-MM-DD format | getBillingDate(): ?string | setBillingDate(?string billingDate): void |
| `billingSequenceNumber` | `?string` | Optional | Sequence of the debit. Depends on Frequency and Billing Attempts Rule. | getBillingSequenceNumber(): ?string | setBillingSequenceNumber(?string billingSequenceNumber): void |
| `displayedReference` | `?string` | Optional | Reference of Pre-debit notification that is displayed to the shopper. Optional field. Maps to reference if missing | getDisplayedReference(): ?string | setDisplayedReference(?string displayedReference): void |
| `merchantAccount` | `string` | Required | The merchant account identifier with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `reference` | `string` | Required | Pre-debit notification reference sent by the merchant. This is a mandatory field | getReference(): string | setReference(string reference): void |
| `shopperReference` | `string` | Required | The ID that uniquely identifies the shopper.<br><br>This `shopperReference` must be the same as the `shopperReference` used in the initial payment. | getShopperReference(): string | setShopperReference(string shopperReference): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |

## Example

```php
use AdyenLib\Models\Builders\NotifyShopperRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$notifyShopperRequest = NotifyShopperRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount6',
    'reference0',
    'shopperReference2'
)
    ->billingDate('billingDate6')
    ->billingSequenceNumber('billingSequenceNumber4')
    ->displayedReference('displayedReference2')
    ->recurringDetailReference('recurringDetailReference4')
    ->storedPaymentMethodId('storedPaymentMethodId8')
    ->build();
```

