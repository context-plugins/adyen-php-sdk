
# Stored Value Result

For each stored value card loaded or reloaded, in the StoredValue response message.
Result of loading/reloading a stored value card.

## Structure

`StoredValueResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `storedValueTransactionType` | [`string(StoredValueTransactionType2Enum)`](../../doc/models/stored-value-transaction-type-2-enum.md) | Required | Identification of operation to proceed on the stored value account or the stored value card.<br>Copy.<br>Possible values:<br><br>* **Activate**<br>* **Duplicate**<br>* **Load**<br>* **Reserve**<br>* **Reverse**<br>* **Unload** | getStoredValueTransactionType(): string | setStoredValueTransactionType(string storedValueTransactionType): void |
| `productCode` | `?int` | Optional | Product code of item purchased with the transaction.<br>Copy.<br><br>**Constraints**: `>= 1`, `<= 20` | getProductCode(): ?int | setProductCode(?int productCode): void |
| `eanUpc` | `?int` | Optional | Standard product code of item purchased with the transaction.<br>Copy. | getEanUpc(): ?int | setEanUpc(?int eanUpc): void |
| `itemAmount` | `?float` | Optional | Total amount of the item line.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getItemAmount(): ?float | setItemAmount(?float itemAmount): void |
| `currency` | `?string` | Optional | Currency of a monetary amount.<br>Copy.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): ?string | setCurrency(?string currency): void |
| `storedValueAccountStatus` | [`?StoredValueAccountStatus1`](../../doc/models/stored-value-account-status-1.md) | Optional | Data related to the result of the stored value card transaction. | getStoredValueAccountStatus(): ?StoredValueAccountStatus1 | setStoredValueAccountStatus(?StoredValueAccountStatus1 storedValueAccountStatus): void |
| `hostTransactionID` | [`?TransactionIDType7`](../../doc/models/transaction-id-type-7.md) | Optional | Identification of the transaction by the host in charge of the stored value transaction.<br>If provided by the Host. | getHostTransactionID(): ?TransactionIDType7 | setHostTransactionID(?TransactionIDType7 hostTransactionID): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueResultBuilder;
use AdyenLib\Models\StoredValueTransactionType2Enum;
use AdyenLib\Models\Builders\StoredValueAccountStatus1Builder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;

$storedValueResult = StoredValueResultBuilder::init(
    StoredValueTransactionType2Enum::LOAD
)
    ->productCode(20)
    ->eanUpc(38)
    ->itemAmount(211.2)
    ->currency('Currency4')
    ->storedValueAccountStatus(
        StoredValueAccountStatus1Builder::init(
            StoredValueAccountIDBuilder::init(
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
            ->currentBalance(45.56)
            ->build()
    )
    ->build();
```

