
# Identification Data 1

Information about the individual's identification document.

## Structure

`IdentificationData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardNumber` | `?string` | Optional | The card number of the document that was issued (AU only). | getCardNumber(): ?string | setCardNumber(?string cardNumber): void |
| `expiryDate` | `?string` | Optional | The expiry date of the document, in YYYY-MM-DD format. | getExpiryDate(): ?string | setExpiryDate(?string expiryDate): void |
| `issuerCountry` | `?string` | Optional | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code where the document was issued. For example, **US**. | getIssuerCountry(): ?string | setIssuerCountry(?string issuerCountry): void |
| `issuerState` | `?string` | Optional | The state or province where the document was issued (AU only). | getIssuerState(): ?string | setIssuerState(?string issuerState): void |
| `nationalIdExempt` | `?bool` | Optional | Applies only to individuals in the US. Set to **true** if the individual does not have an SSN. To verify their identity, Adyen will require them to upload an ID document. | getNationalIdExempt(): ?bool | setNationalIdExempt(?bool nationalIdExempt): void |
| `number` | `?string` | Optional | The number in the document. | getNumber(): ?string | setNumber(?string number): void |
| `type` | [`string(Type132Enum)`](../../doc/models/type-132-enum.md) | Required | Type of identity data. For individuals, the following types are supported. See our [onboarding guide](https://docs.adyen.com/platforms/onboard-users/onboarding-steps/?onboarding_type=custom) for other supported countries.<br><br>- Australia: **driversLicense**, **passport**<br><br>- Hong Kong: **driversLicense**, **nationalIdNumber**, **passport**<br><br>- New Zealand: **driversLicense**, **passport**<br><br>- Singapore: **driversLicense**, **nationalIdNumber**, **passport**<br><br>- All other supported countries: **nationalIdNumber** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\IdentificationData1Builder;
use AdyenLib\Models\Type132Enum;

$identificationData1 = IdentificationData1Builder::init(
    Type132Enum::NATIONALIDNUMBER
)
    ->cardNumber('cardNumber6')
    ->expiryDate('expiryDate8')
    ->issuerCountry('issuerCountry6')
    ->issuerState('issuerState6')
    ->nationalIdExempt(false)
    ->build();
```

