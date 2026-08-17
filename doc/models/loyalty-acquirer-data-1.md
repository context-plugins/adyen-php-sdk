
# Loyalty Acquirer Data 1

Data related to the loyalty Acquirer during a loyalty transaction.
If content not empty.

## Structure

`LoyaltyAcquirerData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyAcquirerID` | `?string` | Optional | Identification of the loyalty Acquirer.<br><br>**Constraints**: *Pattern*: `^.+$` | getLoyaltyAcquirerID(): ?string | setLoyaltyAcquirerID(?string loyaltyAcquirerID): void |
| `approvalCode` | `?string` | Optional | Code assigned to a transaction approval by the Acquirer. Could be an identifier of the approved transaction for the Acquirer. This data element is conditional for the Loyalty Acquirers. Used in the PaymentRequest request for a referral.<br><br>**Constraints**: *Pattern*: `^.+$` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `loyaltyTransactionID` | [`?TransactionIDType`](../../doc/models/transaction-id-type.md) | Optional | Identification of a transaction for the Sale System or the POI System. | getLoyaltyTransactionID(): ?TransactionIDType | setLoyaltyTransactionID(?TransactionIDType loyaltyTransactionID): void |
| `hostReconciliationID` | `?string` | Optional | Identifier of a reconciliation period with a payment or loyalty host. Allows the assignment of a transaction to the Acquirer reconciliation (or batch).<br><br>**Constraints**: *Pattern*: `^.+$` | getHostReconciliationID(): ?string | setHostReconciliationID(?string hostReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyAcquirerData1Builder;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Utils\DateTimeHelper;

$loyaltyAcquirerData1 = LoyaltyAcquirerData1Builder::init()
    ->loyaltyAcquirerID('LoyaltyAcquirerID4')
    ->approvalCode('ApprovalCode4')
    ->loyaltyTransactionID(
        TransactionIDTypeBuilder::init(
            'TransactionID6',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->hostReconciliationID('HostReconciliationID4')
    ->build();
```

