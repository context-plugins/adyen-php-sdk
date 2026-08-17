
# Payment Details Request

## Structure

`PaymentDetailsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authenticationData` | [`?DetailsRequestAuthenticationData1`](../../doc/models/details-request-authentication-data-1.md) | Optional | Data for 3DS authentication. | getAuthenticationData(): ?DetailsRequestAuthenticationData1 | setAuthenticationData(?DetailsRequestAuthenticationData1 authenticationData): void |
| `details` | [`PaymentCompletionDetails1`](../../doc/models/payment-completion-details-1.md) | Required | Use this collection to submit the details that were returned as a result of the `/payments` call. | getDetails(): PaymentCompletionDetails1 | setDetails(PaymentCompletionDetails1 details): void |
| `paymentData` | `?string` | Optional | Encoded payment data. For [authorizing a payment after using 3D Secure 2 Authentication-only](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only/#authorise-the-payment-with-adyen):<br><br>If you received `resultCode`: **AuthenticationNotRequired** in the `/payments` response, use the `threeDSPaymentData` from the same response.<br><br>If you received `resultCode`: **AuthenticationFinished** in the `/payments` response, use the `action.paymentData` from the same response.<br><br>**Constraints**: *Maximum Length*: `200000` | getPaymentData(): ?string | setPaymentData(?string paymentData): void |
| `threeDSAuthenticationOnly` | `?bool` | Optional | Change the `authenticationOnly` indicator originally set in the `/payments` request. Only needs to be set if you want to modify the value set previously. | getThreeDSAuthenticationOnly(): ?bool | setThreeDSAuthenticationOnly(?bool threeDSAuthenticationOnly): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentDetailsRequestBuilder;
use AdyenLib\Models\Builders\PaymentCompletionDetails1Builder;
use AdyenLib\Models\Builders\DetailsRequestAuthenticationData1Builder;

$paymentDetailsRequest = PaymentDetailsRequestBuilder::init(
    PaymentCompletionDetails1Builder::init()
        ->mD('MD4')
        ->paReq('PaReq0')
        ->paRes('PaRes0')
        ->authorizationToken('authorization_token4')
        ->billingToken('billingToken2')
        ->build()
)
    ->authenticationData(
        DetailsRequestAuthenticationData1Builder::init()
            ->authenticationOnly(false)
            ->build()
    )
    ->paymentData('paymentData4')
    ->threeDSAuthenticationOnly(false)
    ->build();
```

