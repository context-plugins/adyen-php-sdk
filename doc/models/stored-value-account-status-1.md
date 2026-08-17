
# Stored Value Account Status 1

Data related to the result of the stored value card transaction.

## Structure

`StoredValueAccountStatus1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `storedValueAccountID` | [`StoredValueAccountID`](../../doc/models/stored-value-account-id.md) | Required | Identification of the stored value account or the stored value card and the associated product sold by the Sale System for stored value requests. | getStoredValueAccountID(): StoredValueAccountID | setStoredValueAccountID(StoredValueAccountID storedValueAccountID): void |
| `currentBalance` | `?float` | Optional | If relevant and known.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCurrentBalance(): ?float | setCurrentBalance(?float currentBalance): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueAccountStatus1Builder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;

$storedValueAccountStatus1 = StoredValueAccountStatus1Builder::init(
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
    ->currentBalance(226.02)
    ->build();
```

