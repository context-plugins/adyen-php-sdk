
# Funds Collection

## Structure

`FundsCollection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountIdentification` | [`?BankAccountIdentification1`](../../doc/models/bank-account-identification-1.md) | Optional | Contains the identification information of the account to which you can transfer funds related to repayments. | getAccountIdentification(): ?BankAccountIdentification1 | setAccountIdentification(?BankAccountIdentification1 accountIdentification): void |
| `fundsCollectionType` | [`?string(FundsCollectionType2Enum)`](../../doc/models/funds-collection-type-2-enum.md) | Optional | The type of funds collection.<br><br>Possible values: **UnscheduledRepayment**, **Revocation**. | getFundsCollectionType(): ?string | setFundsCollectionType(?string fundsCollectionType): void |

## Example

```php
use AdyenLib\Models\Builders\FundsCollectionBuilder;
use AdyenLib\Models\Builders\BankAccountIdentification1Builder;
use AdyenLib\Models\FundsCollectionType2Enum;

$fundsCollection = FundsCollectionBuilder::init()
    ->accountIdentification(
        BankAccountIdentification1Builder::init()
            ->type('BankAccountIdentification1')
            ->build()
    )
    ->fundsCollectionType(FundsCollectionType2Enum::UNSCHEDULEDREPAYMENT)
    ->build();
```

