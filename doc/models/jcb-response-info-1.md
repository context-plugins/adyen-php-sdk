
# JCB Response Info 1

**jcb** details

## Structure

`JCBResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | MID (Merchant ID) number. | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `?bool` | Optional | Indicates whether the JCB Merchant ID is reused from a previously setup JCB payment method. | getReuseMidNumber(): ?bool | setReuseMidNumber(?bool reuseMidNumber): void |
| `serviceLevel` | `?string` | Optional | Specifies the service level (settlement type) of this payment method. | getServiceLevel(): ?string | setServiceLevel(?string serviceLevel): void |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\JCBResponseInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$jCBResponseInfo1 = JCBResponseInfo1Builder::init()
    ->midNumber('midNumber6')
    ->reuseMidNumber(false)
    ->serviceLevel('serviceLevel0')
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

