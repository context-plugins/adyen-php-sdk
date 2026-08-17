
# Donation Payment Response

## Structure

`DonationPaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount26`](../../doc/models/amount-26.md) | Optional | Authorised amount in the transaction. | getAmount(): ?Amount26 | setAmount(?Amount26 amount): void |
| `donationAccount` | `?string` | Optional | The Adyen account name of your charity. We will provide you with this account name once your chosen charity has been [onboarded](https://docs.adyen.com/online-payments/donations#onboarding). | getDonationAccount(): ?string | setDonationAccount(?string donationAccount): void |
| `id` | `?string` | Optional | Your unique resource identifier. | getId(): ?string | setId(?string id): void |
| `merchantAccount` | `?string` | Optional | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `payment` | [`?PaymentResponse9`](../../doc/models/payment-response-9.md) | Optional | Action to be taken for completing the payment. | getPayment(): ?PaymentResponse9 | setPayment(?PaymentResponse9 payment): void |
| `reference` | `?string` | Optional | The reference to uniquely identify a payment. This reference is used in all communication with you about the payment status. We recommend using a unique value per payment; however, it is not a requirement. If you need to provide multiple references for a transaction, separate them with hyphens ("-"). Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status1Enum)`](../../doc/models/status-1-enum.md) | Optional | The status of the donation transaction.<br><br>Possible values:<br><br>* **completed**<br>* **pending**<br>* **refused** | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\DonationPaymentResponseBuilder;
use AdyenLib\Models\Builders\Amount26Builder;
use AdyenLib\Models\Builders\PaymentResponse9Builder;
use AdyenLib\Models\Builders\CheckoutAwaitActionBuilder;
use AdyenLib\Models\Builders\FraudResult1Builder;
use AdyenLib\Models\Builders\FraudCheckResultBuilder;

$donationPaymentResponse = DonationPaymentResponseBuilder::init()
    ->amount(
        Amount26Builder::init(
            'currency2',
            110
        )->build()
    )
    ->donationAccount('donationAccount2')
    ->id('id8')
    ->merchantAccount('merchantAccount0')
    ->payment(
        PaymentResponse9Builder::init()
            ->action(
                CheckoutAwaitActionBuilder::init()
                    ->paymentData('paymentData8')
                    ->paymentMethodType('paymentMethodType8')
                    ->url('url0')
                    ->build()
            )
            ->additionalData(
                [
                    'key0' => 'additionalData6'
                ]
            )
            ->amount(
                Amount26Builder::init(
                    'currency2',
                    110
                )->build()
            )
            ->donationToken('donationToken8')
            ->fraudResult(
                FraudResult1Builder::init(
                    232
                )
                    ->results(
                        [
                            FraudCheckResultBuilder::init(
                                102,
                                246,
                                'name6'
                            )->build(),
                            FraudCheckResultBuilder::init(
                                102,
                                246,
                                'name6'
                            )->build()
                        ]
                    )->build()
            )->build()
    )->build();
```

