
# JCB Response Info

## Structure

`JCBResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | MID (Merchant ID) number. | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `?bool` | Optional | Indicates whether the JCB Merchant ID is reused from a previously setup JCB payment method. | getReuseMidNumber(): ?bool | setReuseMidNumber(?bool reuseMidNumber): void |
| `serviceLevel` | `?string` | Optional | Specifies the service level (settlement type) of this payment method. | getServiceLevel(): ?string | setServiceLevel(?string serviceLevel): void |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\JCBResponseInfoBuilder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$jCBResponseInfo = JCBResponseInfoBuilder::init()
    ->midNumber('midNumber8')
    ->reuseMidNumber(false)
    ->serviceLevel('serviceLevel2')
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

