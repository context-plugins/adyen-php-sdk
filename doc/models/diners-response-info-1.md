
# Diners Response Info 1

**diners** details

## Structure

`DinersResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | MID (Merchant ID) number. | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `?bool` | Optional | Indicates whether the JCB Merchant ID is reused from a previously configured JCB payment method. | getReuseMidNumber(): ?bool | setReuseMidNumber(?bool reuseMidNumber): void |
| `serviceLevel` | `?string` | Optional | The service level (settlement type) of this payment method. Possible values:<br><br>* **noContract**: Adyen holds the contract with JCB.<br>* **gatewayContract**: JCB receives the settlement and handles disputes, then pays out to you or your sub-merchant directly. | getServiceLevel(): ?string | setServiceLevel(?string serviceLevel): void |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DinersResponseInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$dinersResponseInfo1 = DinersResponseInfo1Builder::init()
    ->midNumber('midNumber4')
    ->reuseMidNumber(false)
    ->serviceLevel('serviceLevel8')
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

