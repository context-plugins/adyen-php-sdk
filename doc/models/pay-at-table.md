
# Pay at Table

## Structure

`PayAtTable`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authenticationMethod` | [`?string(AuthenticationMethodEnum)`](../../doc/models/authentication-method-enum.md) | Optional | Allowed authentication methods: Magswipe, Manual Entry. | getAuthenticationMethod(): ?string | setAuthenticationMethod(?string authenticationMethod): void |
| `enablePayAtTable` | `?bool` | Optional | Enable Pay at table. | getEnablePayAtTable(): ?bool | setEnablePayAtTable(?bool enablePayAtTable): void |
| `paymentInstrument` | [`?string(PaymentInstrumentEnum)`](../../doc/models/payment-instrument-enum.md) | Optional | Sets the allowed payment instrument for Pay at table transactions.  Can be: **cash** or **card**. If not set, the terminal presents both options. | getPaymentInstrument(): ?string | setPaymentInstrument(?string paymentInstrument): void |

## Example

```php
use AdyenLib\Models\Builders\PayAtTableBuilder;
use AdyenLib\Models\AuthenticationMethodEnum;
use AdyenLib\Models\PaymentInstrumentEnum;

$payAtTable = PayAtTableBuilder::init()
    ->authenticationMethod(AuthenticationMethodEnum::MAGSWIPE)
    ->enablePayAtTable(false)
    ->paymentInstrument(PaymentInstrumentEnum::CASH)
    ->build();
```

