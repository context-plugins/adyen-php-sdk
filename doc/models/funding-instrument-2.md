
# Funding Instrument 2

Details of the card or token used to fund the pay-in transaction.

## Structure

`FundingInstrument2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardIdentification` | [`?CardIdentification2`](../../doc/models/card-identification-2.md) | Optional | Card details used for the transfer, such as the Primary Account Number (PAN) or stored payment method ID. Required if `sourceOfFunds` is **DEBIT**. Provide either:<br><br>- `storedPaymentMethodId` or<br>- `expiryMonth`, `expiryYear`, and `number`. | getCardIdentification(): ?CardIdentification2 | setCardIdentification(?CardIdentification2 cardIdentification): void |
| `networkPaymentReference` | `?string` | Optional | The unique reference assigned by the card network for the pay-in transaction. | getNetworkPaymentReference(): ?string | setNetworkPaymentReference(?string networkPaymentReference): void |
| `reference` | `?string` | Optional | Your internal reference that identifies this funding instrument. Required if `sourceOfFunds` is **DEPOSIT_ACCOUNT**. | getReference(): ?string | setReference(?string reference): void |
| `sourceOfFunds` | [`?string(SourceOfFundsEnum)`](../../doc/models/source-of-funds-enum.md) | Optional | Indicates where the funds used for the transfer originated. Possible values are:<br><br>- **DEBIT** for card-to-card transfers.<br>- **DEPOSIT_ACCOUNT** for wallet-to-card transfers. | getSourceOfFunds(): ?string | setSourceOfFunds(?string sourceOfFunds): void |

## Example

```php
use AdyenLib\Models\Builders\FundingInstrument2Builder;
use AdyenLib\Models\Builders\CardIdentification2Builder;
use AdyenLib\Models\SourceOfFundsEnum;

$fundingInstrument2 = FundingInstrument2Builder::init()
    ->cardIdentification(
        CardIdentification2Builder::init()
            ->expiryMonth('expiryMonth2')
            ->expiryYear('expiryYear2')
            ->issueNumber('issueNumber0')
            ->number('number6')
            ->startMonth('startMonth8')
            ->build()
    )
    ->networkPaymentReference('networkPaymentReference8')
    ->reference('reference6')
    ->sourceOfFunds(SourceOfFundsEnum::DEBIT)
    ->build();
```

