
# Recurring

The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/classic-integration/recurring-payments)., A container for the type of a recurring contract to be retrieved.

The contract value needs to match the contract value submitted in the payment transaction used to create a recurring contract.
However, if `ONECLICK,RECURRING` is the original contract definition in the initial payment, then `contract` should take either `ONECLICK` or `RECURRING`, depending on whether or not you want the shopper to enter their card's security code when they finalize their purchase., A container for the type of recurring contract to be retrieved.

The recurring.contract must be set to `PAYOUT`, A container for the type of recurring contract to be retrieved.

The `recurring.contract` must be set to "PAYOUT"., The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/classic-integration/recurring-payments)., The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/online-payments/tokenization).

## Structure

`Recurring`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contract` | [`?string(ContractEnum)`](../../doc/models/contract-enum.md) | Optional | The type of recurring contract to be used.<br>Possible values:<br><br>* `ONECLICK` – Payment details can be used to initiate a one-click payment, where the shopper enters the [card security code (CVC/CVV)](https://docs.adyen.com/payments-fundamentals/payment-glossary#card-security-code-cvc-cvv-cid).<br>* `RECURRING` – Payment details can be used without the card security code to initiate [card-not-present transactions](https://docs.adyen.com/payments-fundamentals/payment-glossary#card-not-present-cnp).<br>* `ONECLICK,RECURRING` – Payment details can be used regardless of whether the shopper is on your site or not.<br>* `PAYOUT` – Payment details can be used to [make a payout](https://docs.adyen.com/online-payments/online-payouts).<br>* `EXTERNAL` - Use this when you store payment details and send the raw card number or network token directly in your API request. | getContract(): ?string | setContract(?string contract): void |
| `recurringDetailName` | `?string` | Optional | A descriptive name for this detail. | getRecurringDetailName(): ?string | setRecurringDetailName(?string recurringDetailName): void |
| `recurringExpiry` | `?DateTime` | Optional | Date after which no further authorisations shall be performed. Only for 3D Secure 2. | getRecurringExpiry(): ?\DateTime | setRecurringExpiry(?\DateTime recurringExpiry): void |
| `recurringFrequency` | `?string` | Optional | Minimum number of days between authorisations. Only for 3D Secure 2. | getRecurringFrequency(): ?string | setRecurringFrequency(?string recurringFrequency): void |
| `tokenService` | [`?string(TokenServiceEnum)`](../../doc/models/token-service-enum.md) | Optional | The name of the token service. | getTokenService(): ?string | setTokenService(?string tokenService): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TokenServiceEnum;

$recurring = RecurringBuilder::init()
    ->contract(ContractEnum::ENUM_ONECLICKRECURRING)
    ->recurringDetailName('recurringDetailName2')
    ->recurringExpiry(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->recurringFrequency('recurringFrequency0')
    ->tokenService(TokenServiceEnum::VISATOKENSERVICE)
    ->build();
```

