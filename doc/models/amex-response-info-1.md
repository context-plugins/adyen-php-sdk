
# Amex Response Info 1

**amex** details

## Structure

`AmexResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | Merchant ID (MID) number. | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `?bool` | Optional | Indicates whether the Amex Merchant ID is reused from a previously setup Amex payment method. | getReuseMidNumber(): ?bool | setReuseMidNumber(?bool reuseMidNumber): void |
| `serviceLevel` | `?string` | Optional | The service level (settlement type) of this payment method. Possible values:<br><br>* **noContract**: Adyen holds the contract with American Express.<br>* **gatewayContract**: American Express receives the settlement and handles disputes, then pays out to you or your sub-merchant directly.<br>* **paymentDesignatorContract**: Adyen receives the settlement, and handles disputes and payouts. | getServiceLevel(): ?string | setServiceLevel(?string serviceLevel): void |

## Example

```php
use AdyenLib\Models\Builders\AmexResponseInfo1Builder;

$amexResponseInfo1 = AmexResponseInfo1Builder::init()
    ->midNumber('midNumber2')
    ->reuseMidNumber(false)
    ->serviceLevel('serviceLevel6')
    ->build();
```

