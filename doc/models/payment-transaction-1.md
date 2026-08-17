
# Payment Transaction 1

Data related to the payment and loyalty transaction.

## Structure

`PaymentTransaction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountsReq` | [`AmountsReq`](../../doc/models/amounts-req.md) | Required | Various amounts related to the payment request from the Sale System. | getAmountsReq(): AmountsReq | setAmountsReq(AmountsReq amountsReq): void |
| `originalPOITransaction` | [`?OriginalPOITransaction`](../../doc/models/original-poi-transaction.md) | Optional | Identification of a previous POI transaction.<br>In the Payment Request message, it allows using the card of a previous CardAcquisition or Payment request. | getOriginalPOITransaction(): ?OriginalPOITransaction | setOriginalPOITransaction(?OriginalPOITransaction originalPOITransaction): void |
| `transactionConditions` | [`?TransactionConditions`](../../doc/models/transaction-conditions.md) | Optional | Conditions on which the transaction must be processed. | getTransactionConditions(): ?TransactionConditions | setTransactionConditions(?TransactionConditions transactionConditions): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentTransaction1Builder;
use AdyenLib\Models\Builders\AmountsReqBuilder;
use AdyenLib\Models\Builders\OriginalPOITransactionBuilder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\TransactionConditionsBuilder;
use AdyenLib\Models\LoyaltyHandling1Enum;

$paymentTransaction1 = PaymentTransaction1Builder::init(
    AmountsReqBuilder::init(
        'Currency4',
        38.52
    )
        ->cashBackAmount(77.72)
        ->tipAmount(40.18)
        ->paidAmount(239.98)
        ->minimumAmountToDeliver(73.38)
        ->maximumCashBackAmount(36.82)
        ->build()
)
    ->originalPOITransaction(
        OriginalPOITransactionBuilder::init()
            ->saleID('SaleID6')
            ->pOIID('POIID0')
            ->pOITransactionID(
                TransactionIDType4Builder::init(
                    'TransactionID2',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->reuseCardDataFlag(false)
            ->approvalCode('ApprovalCode0')
            ->build()
    )
    ->transactionConditions(
        TransactionConditionsBuilder::init()
            ->allowedPaymentBrand(
                [
                    'AllowedPaymentBrand0',
                    'AllowedPaymentBrand1',
                    'AllowedPaymentBrand2'
                ]
            )
            ->acquirerID(
                [
                    56,
                    57,
                    58
                ]
            )
            ->debitPreferredFlag(false)
            ->allowedLoyaltyBrand(
                [
                    'AllowedLoyaltyBrand8',
                    'AllowedLoyaltyBrand9'
                ]
            )
            ->loyaltyHandling(LoyaltyHandling1Enum::FORBIDDEN)
            ->build()
    )
    ->build();
```

