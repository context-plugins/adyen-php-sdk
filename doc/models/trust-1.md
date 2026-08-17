
# Trust 1

Information about the trust. Required if `type` is **trust**.

## Structure

`Trust1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `countryOfGoverningLaw` | `string` | Required | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the governing country. | getCountryOfGoverningLaw(): string | setCountryOfGoverningLaw(string countryOfGoverningLaw): void |
| `dateOfIncorporation` | `?string` | Optional | The date when the legal arrangement was incorporated in YYYY-MM-DD format. | getDateOfIncorporation(): ?string | setDateOfIncorporation(?string dateOfIncorporation): void |
| `description` | `?string` | Optional | A short description about the trust. Only applicable for charitable trusts in New Zealand. | getDescription(): ?string | setDescription(?string description): void |
| `doingBusinessAs` | `?string` | Optional | The registered name, if different from the `name`. | getDoingBusinessAs(): ?string | setDoingBusinessAs(?string doingBusinessAs): void |
| `doingBusinessAsAbsent` | `?bool` | Optional | Set this to **true** if the legal arrangement does not have a `Doing business as` name. | getDoingBusinessAsAbsent(): ?bool | setDoingBusinessAsAbsent(?bool doingBusinessAsAbsent): void |
| `name` | `string` | Required | The legal name. | getName(): string | setName(string name): void |
| `principalPlaceOfBusiness` | [`?Address41`](../../doc/models/address-41.md) | Optional | The business address. Required if the principal place of business is different from the `registeredAddress`. | getPrincipalPlaceOfBusiness(): ?Address41 | setPrincipalPlaceOfBusiness(?Address41 principalPlaceOfBusiness): void |
| `registeredAddress` | [`Address51`](../../doc/models/address-51.md) | Required | The address registered at the registrar, such as the Chamber of Commerce. | getRegisteredAddress(): Address51 | setRegisteredAddress(Address51 registeredAddress): void |
| `registrationNumber` | `?string` | Optional | The registration number. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `taxInformation` | [`?(TaxInformation[])`](../../doc/models/tax-information.md) | Optional | The tax information of the entity. | getTaxInformation(): ?array | setTaxInformation(?array taxInformation): void |
| `type` | [`string(Type171Enum)`](../../doc/models/type-171-enum.md) | Required | Type of trust.<br><br>See possible values for trusts in [Australia](https://docs.adyen.com/platforms/verification-requirements/?tab=trust_3_4#trust-types-in-australia) and [New Zealand](https://docs.adyen.com/platforms/verification-requirements/?tab=trust_3_4#trust-types-in-new-zealand). | getType(): string | setType(string type): void |
| `undefinedBeneficiaryInfo` | [`?(UndefinedBeneficiary[])`](../../doc/models/undefined-beneficiary.md) | Optional | The undefined beneficiary information of the entity. | getUndefinedBeneficiaryInfo(): ?array | setUndefinedBeneficiaryInfo(?array undefinedBeneficiaryInfo): void |
| `vatAbsenceReason` | [`?string(VatAbsenceReason1Enum)`](../../doc/models/vat-absence-reason-1-enum.md) | Optional | The reason for not providing a VAT number.<br><br>Possible values: **industryExemption**, **belowTaxThreshold**. | getVatAbsenceReason(): ?string | setVatAbsenceReason(?string vatAbsenceReason): void |
| `vatNumber` | `?string` | Optional | The VAT number. | getVatNumber(): ?string | setVatNumber(?string vatNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Trust1Builder;
use AdyenLib\Models\Builders\Address51Builder;
use AdyenLib\Models\Type171Enum;
use AdyenLib\Models\Builders\Address41Builder;

$trust1 = Trust1Builder::init(
    'countryOfGoverningLaw2',
    'name6',
    Address51Builder::init(
        'country4'
    )
        ->city('city0')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince8')
        ->street('street0')
        ->street2('street24')
        ->build(),
    Type171Enum::DECEASEDESTATE
)
    ->dateOfIncorporation('dateOfIncorporation6')
    ->description('description6')
    ->doingBusinessAs('doingBusinessAs4')
    ->doingBusinessAsAbsent(false)
    ->principalPlaceOfBusiness(
        Address41Builder::init(
            'country6'
        )
            ->city('city8')
            ->postalCode('postalCode6')
            ->stateOrProvince('stateOrProvince0')
            ->street('street2')
            ->street2('street22')
            ->build()
    )
    ->build();
```

