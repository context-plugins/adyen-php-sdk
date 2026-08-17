
# Pin Change Request

## Structure

`PinChangeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encryptedKey` | `string` | Required | The symmetric session key that you encrypted with the [public key](https://docs.adyen.com/api-explorer/balanceplatform/2/get/publicKey) that you received from Adyen. | getEncryptedKey(): string | setEncryptedKey(string encryptedKey): void |
| `encryptedPinBlock` | `string` | Required | The encrypted [PIN block](https://www.pcisecuritystandards.org/glossary/pin-block). | getEncryptedPinBlock(): string | setEncryptedPinBlock(string encryptedPinBlock): void |
| `paymentInstrumentId` | `string` | Required | The unique identifier of the payment instrument, which is the card for which you are managing the PIN. | getPaymentInstrumentId(): string | setPaymentInstrumentId(string paymentInstrumentId): void |
| `token` | `string` | Required | The 16-digit token that you used to generate the `encryptedPinBlock`. | getToken(): string | setToken(string token): void |

## Example

```php
use AdyenLib\Models\Builders\PinChangeRequestBuilder;

$pinChangeRequest = PinChangeRequestBuilder::init(
    'encryptedKey0',
    'encryptedPinBlock2',
    'paymentInstrumentId6',
    'token2'
)->build();
```

