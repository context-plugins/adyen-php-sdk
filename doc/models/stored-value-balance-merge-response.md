
# Stored Value Balance Merge Response

## Structure

`StoredValueBalanceMergeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authCode` | `?string` | Optional | Authorisation code:<br><br>* When the payment is authorised, this field holds the authorisation code for the payment.<br>* When the payment is not authorised, this field is empty. | getAuthCode(): ?string | setAuthCode(?string authCode): void |
| `currentBalance` | [`?Amount`](../../doc/models/amount.md) | Optional | The balance currently on the payment method. | getCurrentBalance(): ?Amount | setCurrentBalance(?Amount currentBalance): void |
| `pspReference` | `?string` | Optional | Adyen's 16-character string reference associated with the transaction/request. This value is globally unique; quote it when communicating with us about this request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `refusalReason` | `?string` | Optional | If the transaction is refused or an error occurs, this field holds Adyen's mapped reason for the refusal or a description of the error.<br><br>When a transaction fails, the authorisation response includes `resultCode` and `refusalReason` values. | getRefusalReason(): ?string | setRefusalReason(?string refusalReason): void |
| `resultCode` | [`?string(ResultCode3Enum)`](../../doc/models/result-code-3-enum.md) | Optional | The result of the payment. Possible values:<br><br>* **Success** – The operation has been completed successfully.<br>* **Refused** – The operation was refused. The reason is given in the `refusalReason` field.<br>* **Error** – There was an error when the operation was processed. The reason is given in the `refusalReason` field.<br>* **NotEnoughBalance** – The amount on the payment method is lower than the amount given in the request. Only applicable to balance checks. | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `thirdPartyRefusalReason` | `?string` | Optional | Raw refusal reason received from the third party, where available | getThirdPartyRefusalReason(): ?string | setThirdPartyRefusalReason(?string thirdPartyRefusalReason): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueBalanceMergeResponseBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\ResultCode3Enum;

$storedValueBalanceMergeResponse = StoredValueBalanceMergeResponseBuilder::init()
    ->authCode('authCode8')
    ->currentBalance(
        AmountBuilder::init(
            'currency2',
            232
        )->build()
    )
    ->pspReference('pspReference6')
    ->refusalReason('refusalReason4')
    ->resultCode(ResultCode3Enum::SUCCESS)
    ->build();
```

