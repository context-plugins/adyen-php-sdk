
# Reversal Request 2

Content of the Reversal Request message.

## Structure

`ReversalRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleData` | [`?SaleData`](../../doc/models/sale-data.md) | Optional | Data associated with the Sale System, with a particular value during the processing of the payment by the POI, including the cards acquisition. | getSaleData(): ?SaleData | setSaleData(?SaleData saleData): void |
| `originalPOITransaction` | [`OriginalPOITransaction2`](../../doc/models/original-poi-transaction-2.md) | Required | Identification of a previous POI transaction. | getOriginalPOITransaction(): OriginalPOITransaction2 | setOriginalPOITransaction(OriginalPOITransaction2 originalPOITransaction): void |
| `reversedAmount` | `?float` | Optional | Amount of the payment or loyalty to reverse.<br>ReversedAmount is implicitly equal to the AuthorizedAmount if absent.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getReversedAmount(): ?float | setReversedAmount(?float reversedAmount): void |
| `reversalReason` | [`string(ReversalReason1Enum)`](../../doc/models/reversal-reason-1-enum.md) | Required | Reason of the payment or loyalty reversal.<br>Possible values:<br><br>* **CustCancel**<br>* **Malfunction**<br>* **MerchantCancel**<br>* **Unable2Compl** | getReversalReason(): string | setReversalReason(string reversalReason): void |

## Example

```php
use AdyenLib\Models\Builders\ReversalRequest2Builder;
use AdyenLib\Models\Builders\OriginalPOITransaction2Builder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ReversalReason1Enum;
use AdyenLib\Models\Builders\SaleDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;

$reversalRequest2 = ReversalRequest2Builder::init(
    OriginalPOITransaction2Builder::init()
        ->saleID('SaleID6')
        ->pOIID('POIID0')
        ->pOITransactionID(
            TransactionIDType4Builder::init(
                'TransactionID2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )->build()
        )
        ->reuseCardDataFlag(true)
        ->approvalCode('ApprovalCode0')
        ->build(),
    ReversalReason1Enum::CUSTCANCEL
)
    ->saleData(
        SaleDataBuilder::init(
            TransactionIDType1Builder::init(
                'TransactionID2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )->build()
        )
            ->operatorID('OperatorID8')
            ->operatorLanguage('OperatorLanguage2')
            ->shiftNumber('ShiftNumber0')
            ->saleReferenceID('SaleReferenceID8')
            ->saleTerminalData(
                SaleTerminalData1Builder::init()
                    ->totalsGroupID('TotalsGroupID4')
                    ->build()
            )
            ->build()
    )
    ->reversedAmount(7.6)
    ->build();
```

