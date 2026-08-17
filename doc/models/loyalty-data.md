
# Loyalty Data

In the Payment, Loyalty or Balance Inquiry Request message, it allows the Sale Terminal to send the identification of the loyalty account or an awarded amount or an amount to redeem to the loyalty account.
Data related to a Loyalty program or account.

## Structure

`LoyaltyData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardAcquisitionReference` | [`?TransactionIDType3`](../../doc/models/transaction-id-type-3.md) | Optional | Reference to the last CardAcquisition, to use the same card.<br>If the loyalty account ID comes from a previous CardAcquisition. | getCardAcquisitionReference(): ?TransactionIDType3 | setCardAcquisitionReference(?TransactionIDType3 cardAcquisitionReference): void |
| `loyaltyAccountID` | [`?LoyaltyAccountID1`](../../doc/models/loyalty-account-id-1.md) | Optional | Identification of a Loyalty account.<br>If loyalty identification of the loyalty account is realised by the Sale System. | getLoyaltyAccountID(): ?LoyaltyAccountID1 | setLoyaltyAccountID(?LoyaltyAccountID1 loyaltyAccountID): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType3Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\LoyaltyAccountID1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\IdentificationSupport1Enum;

$loyaltyData = LoyaltyDataBuilder::init()
    ->cardAcquisitionReference(
        TransactionIDType3Builder::init(
            'TransactionID8',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->loyaltyAccountID(
        LoyaltyAccountID1Builder::init(
            [
                EntryModeEnum::FILE
            ],
            IdentificationType11Enum::ISOTRACK2,
            'LoyaltyID4'
        )
            ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
            ->build()
    )
    ->build();
```

