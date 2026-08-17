
# Cartes Bancaires Response Info 1

**cartesbancaire** details

## Structure

`CartesBancairesResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `siret` | `?string` | Optional | Cartes Bancaires SIRET. Format: 14 digits. | getSiret(): ?string | setSiret(?string siret): void |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\CartesBancairesResponseInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$cartesBancairesResponseInfo1 = CartesBancairesResponseInfo1Builder::init()
    ->siret('siret4')
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

