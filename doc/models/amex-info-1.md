
# Amex Info 1

Details to provide if `type` is **amex**.
For merchants operating in Australia, New Zealand & Canada, JCB and American Express are automatically requested together.

## Structure

`AmexInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | Merchant ID (MID) number. Format: 10 numeric characters.<br>You must provide this field when you request `gatewayContract` or `paymentDesignatorContract` service levels.<br><br>**Constraints**: *Maximum Length*: `10` | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `?bool` | Optional | Indicates whether the Amex Merchant ID is reused from a previously setup Amex payment method.<br>This is only applicable for `gatewayContract` and `paymentDesignatorContract` service levels.<br>The default value is **false**.<br><br>**Default**: `false` | getReuseMidNumber(): ?bool | setReuseMidNumber(?bool reuseMidNumber): void |
| `serviceLevel` | [`string(ServiceLevelEnum)`](../../doc/models/service-level-enum.md) | Required | Specifies the service level (settlement type) of this payment method. Possible values:<br><br>* **noContract**: Adyen holds the contract with American Express.<br>* **gatewayContract**: American Express receives the settlement and handles disputes, then pays out to you or your sub-merchant directly.<br>* **paymentDesignatorContract**: Adyen receives the settlement, and handles disputes and payouts. | getServiceLevel(): string | setServiceLevel(string serviceLevel): void |

## Example

```php
use AdyenLib\Models\Builders\AmexInfo1Builder;
use AdyenLib\Models\ServiceLevelEnum;

$amexInfo1 = AmexInfo1Builder::init(
    ServiceLevelEnum::PAYMENTDESIGNATORCONTRACT
)
    ->midNumber('midNumber6')
    ->reuseMidNumber(false)
    ->build();
```

