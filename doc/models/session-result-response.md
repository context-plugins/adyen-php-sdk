
# Session Result Response

## Structure

`SessionResultResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | Contains additional information about the payment. Some fields are included only if you enable them. To enable these fields in your Customer Area, go to **Developers** > **Additional data**. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `id` | `?string` | Optional | A unique identifier of the session. | getId(): ?string | setId(?string id): void |
| `payments` | [`?(Payment[])`](../../doc/models/payment.md) | Optional | A list of all authorised payments done for this session. | getPayments(): ?array | setPayments(?array payments): void |
| `reference` | `?string` | Optional | The unique reference that you provided in the original `/sessions` request. This identifies the payment and is used in all communication with you about the payment status. | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status5Enum)`](../../doc/models/status-5-enum.md) | Optional | The status of the session. The status included in the response doesn't get updated. Don't make the request again to check for payment status updates.<br><br>Possible values:<br><br>* **completed**: the shopper completed the payment, and the payment was authorized.<br>* **paymentPending**: the shopper is in the process of making the payment. This applies to payment methods with an asynchronous flow, like voucher payments where the shopper completes the payment in a physical shop.<br>* **refused**: the session has been refused, because of too many refused payment attempts. The shopper can no longer complete the payment with this session.<br>* **canceled**: the shopper canceled the payment.<br>* **expired**: the session expired. The shopper can no longer complete the payment with this session. By default, the session expires one hour after it is created. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\SessionResultResponseBuilder;
use AdyenLib\Models\Builders\PaymentBuilder;
use AdyenLib\Models\Builders\Amount26Builder;
use AdyenLib\Models\Builders\PaymentResponse3Builder;
use AdyenLib\Models\ResultCode2Enum;
use AdyenLib\Models\Status5Enum;

$sessionResultResponse = SessionResultResponseBuilder::init()
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData5'
        ]
    )
    ->id('id4')
    ->payments(
        [
            PaymentBuilder::init()
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
                ->pspReference('pspReference6')
                ->resultCode(ResultCode2Enum::PENDING)
                ->build()
        ]
    )
    ->reference('reference0')
    ->status(Status5Enum::ACTIVE)
    ->build();
```

