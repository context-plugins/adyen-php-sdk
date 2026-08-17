
# Checkout SDK Action

## Structure

`CheckoutSDKAction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentData` | `?string` | Optional | Encoded payment data. | getPaymentData(): ?string | setPaymentData(?string paymentData): void |
| `paymentMethodType` | `?string` | Optional | Specifies the payment method. | getPaymentMethodType(): ?string | setPaymentMethodType(?string paymentMethodType): void |
| `sdkData` | `?array<string,string>` | Optional | The data to pass to the SDK. | getSdkData(): ?array | setSdkData(?array sdkData): void |
| `type` | [`string(Type19Enum)`](../../doc/models/type-19-enum.md) | Required | The type of the action. | getType(): string | setType(string type): void |
| `url` | `?string` | Optional | Specifies the URL to redirect to. | getUrl(): ?string | setUrl(?string url): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutSDKActionBuilder;
use AdyenLib\Models\Type19Enum;

$checkoutSDKAction = CheckoutSDKActionBuilder::init(
    Type19Enum::SDK
)
    ->paymentData('paymentData4')
    ->paymentMethodType('paymentMethodType4')
    ->sdkData(
        [
            'key0' => 'sdkData7'
        ]
    )
    ->url('url6')
    ->build();
```

