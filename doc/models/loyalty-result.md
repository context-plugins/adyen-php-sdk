
# Loyalty Result

Data related to the result of a processed loyalty transaction.
In the Message Response, the result of each loyalty brand transaction.

## Structure

`LoyaltyResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyAccount` | [`LoyaltyAccount1`](../../doc/models/loyalty-account-1.md) | Required | Data related to a loyalty account processed in the transaction. | getLoyaltyAccount(): LoyaltyAccount1 | setLoyaltyAccount(LoyaltyAccount1 loyaltyAccount): void |
| `currentBalance` | `?float` | Optional | Balance of an account.<br>If known (provided by the card or an external host).<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCurrentBalance(): ?float | setCurrentBalance(?float currentBalance): void |
| `loyaltyAcquirerData` | [`?LoyaltyAcquirerData1`](../../doc/models/loyalty-acquirer-data-1.md) | Optional | Data related to the loyalty Acquirer during a loyalty transaction.<br>If content not empty. | getLoyaltyAcquirerData(): ?LoyaltyAcquirerData1 | setLoyaltyAcquirerData(?LoyaltyAcquirerData1 loyaltyAcquirerData): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyResultBuilder;
use AdyenLib\Models\Builders\LoyaltyAccount1Builder;
use AdyenLib\Models\Builders\LoyaltyAccountID2Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\IdentificationSupport1Enum;
use AdyenLib\Models\Builders\LoyaltyAcquirerData1Builder;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Utils\DateTimeHelper;

$loyaltyResult = LoyaltyResultBuilder::init(
    LoyaltyAccount1Builder::init(
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
        ->loyaltyBrand('LoyaltyBrand0')
        ->build()
)
    ->currentBalance(140.52)
    ->loyaltyAcquirerData(
        LoyaltyAcquirerData1Builder::init()
            ->loyaltyAcquirerID('LoyaltyAcquirerID4')
            ->approvalCode('ApprovalCode4')
            ->loyaltyTransactionID(
                TransactionIDTypeBuilder::init(
                    'TransactionID6',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->hostReconciliationID('HostReconciliationID4')
            ->build()
    )
    ->build();
```

