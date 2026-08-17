
# Stored Payment Method 4

## Structure

`StoredPaymentMethod4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `pixRecurring` | [`?PixRecurring`](../../doc/models/pix-recurring.md) | Optional | - | getPixRecurring(): ?PixRecurring | setPixRecurring(?PixRecurring pixRecurring): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type44Enum)`](../../doc/models/type-44-enum.md) | Optional | The payment method type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod4Builder;
use AdyenLib\Models\Builders\PixRecurringBuilder;
use AdyenLib\Models\Frequency2Enum;
use AdyenLib\Models\Builders\Amount42Builder;

$storedPaymentMethod4 = StoredPaymentMethod4Builder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->pixRecurring(
        PixRecurringBuilder::init()
            ->billingDate('billingDate0')
            ->businessDayOnly(false)
            ->endsAt('endsAt8')
            ->frequency(Frequency2Enum::YEARLY)
            ->minAmount(
                Amount42Builder::init(
                    'currency6',
                    156
                )->build()
            )->build()
    )
    ->recurringDetailReference('recurringDetailReference6')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->build();
```

