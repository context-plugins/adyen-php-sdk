
# Payment

## Structure

`Payment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount26`](../../doc/models/amount-26.md) | Optional | Authorised amount in the transaction. | getAmount(): ?Amount26 | setAmount(?Amount26 amount): void |
| `paymentMethod` | [`?PaymentResponse3`](../../doc/models/payment-response-3.md) | Optional | Only returned for `resultCode`: **Authorised**.<br>Details about the payment method used in the transaction. | getPaymentMethod(): ?PaymentResponse3 | setPaymentMethod(?PaymentResponse3 paymentMethod): void |
| `pspReference` | `?string` | Optional | Adyen's 16-character reference associated with the transaction/request. This value is globally unique. Use this reference when you communicate with us about this request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | [`?string(ResultCode2Enum)`](../../doc/models/result-code-2-enum.md) | Optional | The result of the payment. For more information, see [Result codes](https://docs.adyen.com/online-payments/payment-result-codes).<br><br>Possible values:<br><br>* **Authorised** – The payment was successfully authorised. This state serves as an indicator to proceed with the delivery of goods and services. This is a final state.<br>* **Received** – Indicates the payment request was successfully received by Adyen, and will be processed. This is the initial state for all payments.<br>* **Pending** – The payment order was successfully received but the final status of the payment is not available yet. This is common for payment methods with an asynchronous flow. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentBuilder;
use AdyenLib\Models\Builders\Amount26Builder;
use AdyenLib\Models\Builders\PaymentResponse3Builder;
use AdyenLib\Models\ResultCode2Enum;

$payment = PaymentBuilder::init()
    ->amount(
        Amount26Builder::init(
            'currency2',
            110
        )->build()
    )
    ->paymentMethod(
        PaymentResponse3Builder::init()
            ->brand('brand6')
            ->type('type8')
            ->build()
    )
    ->pspReference('pspReference2')
    ->resultCode(ResultCode2Enum::AUTHORISED)
    ->build();
```

