
# Checkout Forward Request

## Structure

`CheckoutForwardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount11`](../../doc/models/amount-11.md) | Optional | The amount of the forwarded payment. | getAmount(): ?Amount11 | setAmount(?Amount11 amount): void |
| `baseUrl` | `string` | Required | The base URL of the third party API, where Adyen will send the request to forward the payment details. | getBaseUrl(): string | setBaseUrl(string baseUrl): void |
| `merchantAccount` | `string` | Required | Your merchant account. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantReference` | `?string` | Optional | Merchant defined payment reference. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `options` | [`?CheckoutForwardRequestOptions2`](../../doc/models/checkout-forward-request-options-2.md) | Optional | The customizations that can be applied when making a forward request. | getOptions(): ?CheckoutForwardRequestOptions2 | setOptions(?CheckoutForwardRequestOptions2 options): void |
| `paymentMethod` | [`?CheckoutForwardRequestCard2`](../../doc/models/checkout-forward-request-card-2.md) | Optional | The card details. | getPaymentMethod(): ?CheckoutForwardRequestCard2 | setPaymentMethod(?CheckoutForwardRequestCard2 paymentMethod): void |
| `request` | [`CheckoutOutgoingForwardRequest2`](../../doc/models/checkout-outgoing-forward-request-2.md) | Required | The [details of the request](https://docs.adyen.com/online-payments/tokenization/forward-payment-details#request-to-adyen-card) that you want to forward to the third-party. | getRequest(): CheckoutOutgoingForwardRequest2 | setRequest(CheckoutOutgoingForwardRequest2 request): void |
| `shopperReference` | `string` | Required | Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): string | setShopperReference(string shopperReference): void |
| `storedPaymentMethodId` | `?string` | Optional | The unique identifier of the token that you want to forward to the third party. This is the `storedPaymentMethodId` you received in the webhook after you created the token. | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutForwardRequestBuilder;
use AdyenLib\Models\Builders\CheckoutOutgoingForwardRequest2Builder;
use AdyenLib\Models\HttpMethodEnum;
use AdyenLib\Models\Builders\Amount11Builder;
use AdyenLib\Models\Builders\CheckoutForwardRequestOptions2Builder;
use AdyenLib\Models\Builders\CheckoutNetworkTokenOption2Builder;
use AdyenLib\Models\Builders\CheckoutForwardRequestCard2Builder;

$checkoutForwardRequest = CheckoutForwardRequestBuilder::init(
    'baseUrl2',
    'merchantAccount6',
    CheckoutOutgoingForwardRequest2Builder::init(
        'body2',
        HttpMethodEnum::POST
    )
        ->credentials('credentials0')
        ->headers(
            [
                'key0' => 'headers9'
            ]
        )
        ->urlSuffix('urlSuffix2')
        ->build(),
    'shopperReference2'
)
    ->amount(
        Amount11Builder::init(
            'currency2',
            110
        )->build()
    )
    ->merchantReference('merchantReference8')
    ->options(
        CheckoutForwardRequestOptions2Builder::init()
            ->accountUpdate(false)
            ->dryRun(false)
            ->networkToken(
                CheckoutNetworkTokenOption2Builder::init()
                    ->includeCryptogram(false)
                    ->useNetworkToken(false)
                    ->build()
            )
            ->networkTxReferencePaths(
                [
                    'networkTxReferencePaths7'
                ]
            )
            ->tokenize(false)
            ->build()
    )
    ->paymentMethod(
        CheckoutForwardRequestCard2Builder::init()
            ->cvc('cvc6')
            ->encryptedCardNumber('encryptedCardNumber0')
            ->encryptedExpiryMonth('encryptedExpiryMonth2')
            ->encryptedExpiryYear('encryptedExpiryYear2')
            ->encryptedSecurityCode('encryptedSecurityCode2')
            ->build()
    )
    ->storedPaymentMethodId('storedPaymentMethodId8')
    ->build();
```

