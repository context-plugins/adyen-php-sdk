
# Diners Info 1

Details to provide if `type` is **diners**.
For merchants operating in Japan, Diners payments are processed through the JCB network. This means that you must include [JCB-specific fields](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/paymentMethodSettings/(paymentMethodId)#request-jcb) in this object.

## Structure

`DinersInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `midNumber` | `?string` | Optional | MID (Merchant ID) number. Required for merchants operating in Japan.<br>Format: 14 numeric characters.<br><br>**Constraints**: *Maximum Length*: `14` | getMidNumber(): ?string | setMidNumber(?string midNumber): void |
| `reuseMidNumber` | `bool` | Required | Indicates whether the JCB Merchant ID is reused from a previously configured JCB payment method.<br>The default value is **false**.<br>For merchants operating in Japan, this field is required and must be set to **true**.<br><br>**Default**: `false` | getReuseMidNumber(): bool | setReuseMidNumber(bool reuseMidNumber): void |
| `serviceLevel` | [`?string(ServiceLevel1Enum)`](../../doc/models/service-level-1-enum.md) | Optional | Specifies the service level (settlement type) of this payment method. Required for merchants operating in Japan. Possible values:<br><br>* **noContract**: Adyen holds the contract with JCB.<br>* **gatewayContract**: JCB receives the settlement and handles disputes, then pays out to you or your sub-merchant directly. | getServiceLevel(): ?string | setServiceLevel(?string serviceLevel): void |
| `transactionDescription` | [`?TransactionDescriptionInfo1`](../../doc/models/transaction-description-info-1.md) | Optional | Information regarding the transaction description.<br><br>> You cannot configure the transaction description in the test environment. | getTransactionDescription(): ?TransactionDescriptionInfo1 | setTransactionDescription(?TransactionDescriptionInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DinersInfo1Builder;
use AdyenLib\Models\ServiceLevel1Enum;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;

$dinersInfo1 = DinersInfo1Builder::init(
    false
)
    ->midNumber('midNumber8')
    ->serviceLevel(ServiceLevel1Enum::NOCONTRACT)
    ->transactionDescription(
        TransactionDescriptionInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

