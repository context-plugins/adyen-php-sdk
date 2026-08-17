
# Reveal Pin Request

## Structure

`RevealPinRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encryptedKey` | `string` | Required | The symmetric session key that you encrypted with the [public key](https://docs.adyen.com/api-explorer/balanceplatform/2/get/publicKey) that you received from Adyen. | getEncryptedKey(): string | setEncryptedKey(string encryptedKey): void |
| `paymentInstrumentId` | `string` | Required | The unique identifier of the payment instrument, which is the card for which you are managing the PIN. | getPaymentInstrumentId(): string | setPaymentInstrumentId(string paymentInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\RevealPinRequestBuilder;

$revealPinRequest = RevealPinRequestBuilder::init(
    'encryptedKey6',
    'paymentInstrumentId2'
)->build();
```

