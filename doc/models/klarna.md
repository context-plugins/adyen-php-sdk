
# Klarna

## Structure

`Klarna`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billingAddress` | `?string` | Optional | The address where to send the invoice. | getBillingAddress(): ?string | setBillingAddress(?string billingAddress): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `deliveryAddress` | `?string` | Optional | The address where the goods should be delivered. | getDeliveryAddress(): ?string | setDeliveryAddress(?string deliveryAddress): void |
| `merchantData` | `?string` | Optional | Base64-encoded merchant metadata (Extra Merchant Data) forwarded to Klarna at authorization.<br><br>**Constraints**: *Maximum Length*: `10240` | getMerchantData(): ?string | setMerchantData(?string merchantData): void |
| `personalDetails` | `?string` | Optional | Shopper name, date of birth, phone number, and email address. | getPersonalDetails(): ?string | setPersonalDetails(?string personalDetails): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `subtype` | `?string` | Optional | The type of flow to initiate. | getSubtype(): ?string | setSubtype(?string subtype): void |
| `type` | [`string(Type34Enum)`](../../doc/models/type-34-enum.md) | Required | **klarna**<br><br>**Default**: `Type34Enum::KLARNA` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\KlarnaBuilder;
use AdyenLib\Models\Type34Enum;

$klarna = KlarnaBuilder::init(
    Type34Enum::KLARNA
)
    ->billingAddress('billingAddress8')
    ->checkoutAttemptId('checkoutAttemptId6')
    ->deliveryAddress('deliveryAddress6')
    ->merchantData('merchantData4')
    ->personalDetails('personalDetails8')
    ->build();
```

