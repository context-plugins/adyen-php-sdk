
# Stored Value Data

It contains: - the identification of the stored value accounts or the stored value cards, if provided by the Sale System, and - the associated products sold by the Sale System.
Data related to the stored value card.

## Structure

`StoredValueData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `storedValueProvider` | `?string` | Optional | Identification of the provider of the stored value account load/reload.<br>If more than one provider to manage on the POI, and StoredValueAccountID absent.<br><br>**Constraints**: *Pattern*: `^.+$` | getStoredValueProvider(): ?string | setStoredValueProvider(?string storedValueProvider): void |
| `storedValueTransactionType` | [`string(StoredValueTransactionType1Enum)`](../../doc/models/stored-value-transaction-type-1-enum.md) | Required | Identification of operation to proceed on the stored value account or the stored value card.<br>Possible values:<br><br>* **Activate**<br>* **Duplicate**<br>* **Load**<br>* **Reserve**<br>* **Reverse**<br>* **Unload** | getStoredValueTransactionType(): string | setStoredValueTransactionType(string storedValueTransactionType): void |
| `storedValueAccountID` | [`?StoredValueAccountID1`](../../doc/models/stored-value-account-id-1.md) | Optional | Identification of the stored value account or the stored value card.<br>If the identification of the Stored Value account or card has been made by the Sale System before the request. | getStoredValueAccountID(): ?StoredValueAccountID1 | setStoredValueAccountID(?StoredValueAccountID1 storedValueAccountID): void |
| `originalPOITransaction` | [`?OriginalPOITransaction1`](../../doc/models/original-poi-transaction-1.md) | Optional | Identification of a previous POI transaction.<br>If StoredValueTransactionType is Reverse or Duplicate. | getOriginalPOITransaction(): ?OriginalPOITransaction1 | setOriginalPOITransaction(?OriginalPOITransaction1 originalPOITransaction): void |
| `productCode` | `?int` | Optional | Product code of item purchased with the transaction.<br><br>**Constraints**: `>= 1`, `<= 20` | getProductCode(): ?int | setProductCode(?int productCode): void |
| `eanUpc` | `?int` | Optional | Standard product code of item purchased with the transaction. | getEanUpc(): ?int | setEanUpc(?int eanUpc): void |
| `itemAmount` | `?float` | Optional | Total amount of the item line.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getItemAmount(): ?float | setItemAmount(?float itemAmount): void |
| `currency` | `?string` | Optional | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): ?string | setCurrency(?string currency): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueDataBuilder;
use AdyenLib\Models\StoredValueTransactionType1Enum;
use AdyenLib\Models\Builders\StoredValueAccountID1Builder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\OriginalPOITransaction1Builder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Utils\DateTimeHelper;

$storedValueData = StoredValueDataBuilder::init(
    StoredValueTransactionType1Enum::RESERVE
)
    ->storedValueProvider('StoredValueProvider8')
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
    ->eanUpc(18)
    ->build();
```

