
# Klarna Network

## Structure

`KlarnaNetwork`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `klarnaNetworkData` | `?string` | Optional | A string containing a structured JSON object. This is a passthrough field used to enable custom features or data exchange with Klarna.<br><br>**Constraints**: *Maximum Length*: `10240` | getKlarnaNetworkData(): ?string | setKlarnaNetworkData(?string klarnaNetworkData): void |
| `klarnaNetworkSessionToken` | `?string` | Optional | The token obtained from the Klarna SDK during an Express Checkout flow.<br><br>**Constraints**: *Maximum Length*: `10240` | getKlarnaNetworkSessionToken(): ?string | setKlarnaNetworkSessionToken(?string klarnaNetworkSessionToken): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | `string` | Required, Constant | **klarna_network**<br><br>**Value**: `'klarna_network'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\KlarnaNetworkBuilder;

$klarnaNetwork = KlarnaNetworkBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId8')
    ->klarnaNetworkData('klarnaNetworkData8')
    ->klarnaNetworkSessionToken('klarnaNetworkSessionToken4')
    ->recurringDetailReference('recurringDetailReference2')
    ->sdkData('sdkData8')
    ->build();
```

