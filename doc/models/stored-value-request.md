
# Stored Value Request

It conveys Information related to the Stored Value transaction to process.
Content of the Stored Value Request message.

## Structure

`StoredValueRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleData` | [`SaleData1`](../../doc/models/sale-data-1.md) | Required | Data related to the Sale System. | getSaleData(): SaleData1 | setSaleData(SaleData1 saleData): void |
| `storedValueData` | [`StoredValueData[]`](../../doc/models/stored-value-data.md) | Required | Data related to the stored value card. | getStoredValueData(): array | setStoredValueData(array storedValueData): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueRequestBuilder;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\StoredValueDataBuilder;
use AdyenLib\Models\StoredValueTransactionType1Enum;
use AdyenLib\Models\Builders\StoredValueAccountID1Builder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\OriginalPOITransaction1Builder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;

$storedValueRequest = StoredValueRequestBuilder::init(
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
    [
        StoredValueDataBuilder::init(
            StoredValueTransactionType1Enum::RESERVE
        )
            ->storedValueProvider('StoredValueProvider2')
            ->storedValueAccountID(
                StoredValueAccountID1Builder::init(
                    StoredValueAccountType1Enum::PHONECARD,
                    [
                        EntryModeEnum::MAGSTRIPE,
                        EntryModeEnum::SCANNED
                    ],
                    IdentificationType11Enum::PHONENUMBER,
                    'StoredValueID8'
                )
                    ->storedValueProvider('StoredValueProvider4')
                    ->ownerName('OwnerName0')
                    ->expiryDate(4)
                    ->build()
            )
            ->originalPOITransaction(
                OriginalPOITransaction1Builder::init()
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
            ->productCode(20)
            ->eanUpc(194)
            ->build()
    ]
)->build();
```

