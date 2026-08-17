
# UPI Intent

## Structure

`UPIIntent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appId` | `?string` | Optional | TPAP (Third Party Application) Id that is being used to make the UPI payment | getAppId(): ?string | setAppId(?string appId): void |
| `billingSequenceNumber` | `?string` | Optional | The sequence number for the debit. For example, send **2** if this is the second debit for the subscription. The sequence number is included in the notification sent to the shopper. | getBillingSequenceNumber(): ?string | setBillingSequenceNumber(?string billingSequenceNumber): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `shopperNotificationReference` | `?string` | Optional | The `shopperNotificationReference` returned in the response when you requested to notify the shopper. Used for recurring payment only. | getShopperNotificationReference(): ?string | setShopperNotificationReference(?string shopperNotificationReference): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | `string` | Required, Constant | **upi_intent**<br><br>**Value**: `'upi_intent'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\UPIIntentBuilder;

$uPIIntent = UPIIntentBuilder::init()
    ->appId('appId8')
    ->billingSequenceNumber('billingSequenceNumber2')
    ->checkoutAttemptId('checkoutAttemptId8')
    ->recurringDetailReference('recurringDetailReference2')
    ->sdkData('sdkData8')
    ->build();
```

