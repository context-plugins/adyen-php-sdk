
# Loyalty Account 1

Data related to a loyalty account processed in the transaction.

## Structure

`LoyaltyAccount1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyAccountID` | [`LoyaltyAccountID2`](../../doc/models/loyalty-account-id-2.md) | Required | Identification of a Loyalty account. | getLoyaltyAccountID(): LoyaltyAccountID2 | setLoyaltyAccountID(LoyaltyAccountID2 loyaltyAccountID): void |
| `loyaltyBrand` | `?string` | Optional | Identification of a Loyalty brand.<br>If a card is analysed.<br><br>**Constraints**: *Pattern*: `^.+$` | getLoyaltyBrand(): ?string | setLoyaltyBrand(?string loyaltyBrand): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyAccount1Builder;
use AdyenLib\Models\Builders\LoyaltyAccountID2Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\IdentificationSupport1Enum;

$loyaltyAccount1 = LoyaltyAccount1Builder::init(
    LoyaltyAccountID2Builder::init(
        [
            EntryModeEnum::FILE
        ],
        IdentificationType11Enum::ISOTRACK2,
        'LoyaltyID4'
    )
        ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
        ->build()
)
    ->loyaltyBrand('LoyaltyBrand4')
    ->build();
```

