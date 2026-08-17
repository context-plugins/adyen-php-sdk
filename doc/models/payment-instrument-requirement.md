
# Payment Instrument Requirement

## Structure

`PaymentInstrumentRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Specifies the requirements for the payment instrument that need to be included in the request for a particular route. | getDescription(): ?string | setDescription(?string description): void |
| `issuingCountryCode` | `?string` | Optional | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code where the payment instrument is issued. For example, **NL** or **US**. | getIssuingCountryCode(): ?string | setIssuingCountryCode(?string issuingCountryCode): void |
| `issuingCountryCodes` | `?(string[])` | Optional | The two-character ISO-3166-1 alpha-2 country code list for payment instruments. | getIssuingCountryCodes(): ?array | setIssuingCountryCodes(?array issuingCountryCodes): void |
| `onlyForCrossBalancePlatform` | `?bool` | Optional | Specifies if the requirement only applies to transfers to another balance platform. | getOnlyForCrossBalancePlatform(): ?bool | setOnlyForCrossBalancePlatform(?bool onlyForCrossBalancePlatform): void |
| `paymentInstrumentType` | [`?string(PaymentInstrumentTypeEnum)`](../../doc/models/payment-instrument-type-enum.md) | Optional | The type of the payment instrument. For example, "BankAccount" or "Card". | getPaymentInstrumentType(): ?string | setPaymentInstrumentType(?string paymentInstrumentType): void |
| `type` | `string` | Required, Constant | **paymentInstrumentRequirement**<br><br>**Value**: `'paymentInstrumentRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentRequirementBuilder;
use AdyenLib\Models\PaymentInstrumentTypeEnum;

$paymentInstrumentRequirement = PaymentInstrumentRequirementBuilder::init()
    ->description('description2')
    ->issuingCountryCode('issuingCountryCode0')
    ->issuingCountryCodes(
        [
            'issuingCountryCodes1',
            'issuingCountryCodes2'
        ]
    )
    ->onlyForCrossBalancePlatform(false)
    ->paymentInstrumentType(PaymentInstrumentTypeEnum::BANKACCOUNT)
    ->build();
```

