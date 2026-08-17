
# Card Acquisition Request

It conveys Information related to the payment and loyalty cards to read and analyse. This message pair is usually followed by a message pair (e.g. payment or loyalty) which refers to this Card Acquisition message pair.
Content of the Card Acquisition Request message.

## Structure

`CardAcquisitionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleData` | [`SaleData1`](../../doc/models/sale-data-1.md) | Required | Data related to the Sale System. | getSaleData(): SaleData1 | setSaleData(SaleData1 saleData): void |
| `cardAcquisitionTransaction` | [`CardAcquisitionTransaction1`](../../doc/models/card-acquisition-transaction-1.md) | Required | Data related to the payment and loyalty card acquisition. | getCardAcquisitionTransaction(): CardAcquisitionTransaction1 | setCardAcquisitionTransaction(CardAcquisitionTransaction1 cardAcquisitionTransaction): void |

## Example

```php
use AdyenLib\Models\Builders\CardAcquisitionRequestBuilder;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\CardAcquisitionTransaction1Builder;
use AdyenLib\Models\LoyaltyHandling2Enum;
use AdyenLib\Models\ForceEntryModeEnum;

$cardAcquisitionRequest = CardAcquisitionRequestBuilder::init(
    SaleData1Builder::init(
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
        ->build(),
    CardAcquisitionTransaction1Builder::init()
        ->allowedPaymentBrand(
            [
                'AllowedPaymentBrand6',
                'AllowedPaymentBrand7'
            ]
        )
        ->allowedLoyaltyBrand(
            [
                'AllowedLoyaltyBrand4'
            ]
        )
        ->loyaltyHandling(LoyaltyHandling2Enum::PROCESSED)
        ->customerLanguage('CustomerLanguage8')
        ->forceEntryMode(
            [
                ForceEntryModeEnum::ICC
            ]
        )
        ->build()
)->build();
```

