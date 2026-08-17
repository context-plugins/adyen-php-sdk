
# Loyalty Account Req

## Structure

`LoyaltyAccountReq`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardAcquisitionReference` | [`?TransactionIDType`](../../doc/models/transaction-id-type.md) | Optional | Identification of a transaction for the Sale System or the POI System. | getCardAcquisitionReference(): ?TransactionIDType | setCardAcquisitionReference(?TransactionIDType cardAcquisitionReference): void |
| `loyaltyAccountID` | [`?LoyaltyAccountID`](../../doc/models/loyalty-account-id.md) | Optional | Identification of a Loyalty account.<br>In the Payment Request message, it allows to identify the loyalty account by the Sale Terminal instead of the POI Terminal (e.g. because the account identification is a bar-code read by the Cashier on a scanner device). | getLoyaltyAccountID(): ?LoyaltyAccountID | setLoyaltyAccountID(?LoyaltyAccountID loyaltyAccountID): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyAccountReqBuilder;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\LoyaltyAccountIDBuilder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\IdentificationSupport1Enum;

$loyaltyAccountReq = LoyaltyAccountReqBuilder::init()
    ->cardAcquisitionReference(
        TransactionIDTypeBuilder::init(
            'TransactionID8',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->loyaltyAccountID(
        LoyaltyAccountIDBuilder::init(
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

