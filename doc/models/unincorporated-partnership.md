
# Unincorporated Partnership

## Structure

`UnincorporatedPartnership`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `countryOfGoverningLaw` | `string` | Required | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the governing country. | getCountryOfGoverningLaw(): string | setCountryOfGoverningLaw(string countryOfGoverningLaw): void |
| `dateOfIncorporation` | `?string` | Optional | The date when the legal arrangement was incorporated in YYYY-MM-DD format. | getDateOfIncorporation(): ?string | setDateOfIncorporation(?string dateOfIncorporation): void |
| `description` | `?string` | Optional | Short description about the Legal Arrangement. | getDescription(): ?string | setDescription(?string description): void |
| `doingBusinessAs` | `?string` | Optional | The registered name, if different from the `name`. | getDoingBusinessAs(): ?string | setDoingBusinessAs(?string doingBusinessAs): void |
| `doingBusinessAsAbsent` | `?bool` | Optional | Set this to **true** if the legal arrangement does not have a `Doing business as` name. | getDoingBusinessAsAbsent(): ?bool | setDoingBusinessAsAbsent(?bool doingBusinessAsAbsent): void |
| `name` | `string` | Required | The legal name. | getName(): string | setName(string name): void |
| `principalPlaceOfBusiness` | [`?Address41`](../../doc/models/address-41.md) | Optional | The business address. Required if the principal place of business is different from the `registeredAddress`. | getPrincipalPlaceOfBusiness(): ?Address41 | setPrincipalPlaceOfBusiness(?Address41 principalPlaceOfBusiness): void |
| `registeredAddress` | [`Address51`](../../doc/models/address-51.md) | Required | The address registered at the registrar, such as the Chamber of Commerce. | getRegisteredAddress(): Address51 | setRegisteredAddress(Address51 registeredAddress): void |
| `registrationNumber` | `?string` | Optional | The registration number. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `taxInformation` | [`?(TaxInformation[])`](../../doc/models/tax-information.md) | Optional | The tax information of the entity. | getTaxInformation(): ?array | setTaxInformation(?array taxInformation): void |
| `type` | [`?string(Type191Enum)`](../../doc/models/type-191-enum.md) | Optional, Read-only | Type of Partnership.<br><br>Possible values:<br><br>* **limitedPartnership**<br>* **generalPartnership**<br>* **familyPartnership**<br>* **commercialPartnership**<br>* **publicPartnership**<br>* **otherPartnership**<br>* **gbr**<br>* **gmbh**<br>* **kgaa**<br>* **cv**<br>* **vof**<br>* **maatschap**<br>* **privateFundLimitedPartnership**<br>* **businessTrustEntity**<br>* **businessPartnership**<br>* **limitedLiabilityPartnership**<br>* **eg**<br>* **cooperative**<br>* **vos**<br>* **comunidadDeBienes**<br>* **herenciaYacente**<br>* **comunidadDePropietarios**<br>* **sep**<br>* **sca**<br>* **bt**<br>* **kkt**<br>* **scs**<br>* **snc** | getType(): ?string | setType(?string type): void |
| `vatAbsenceReason` | [`?string(VatAbsenceReason1Enum)`](../../doc/models/vat-absence-reason-1-enum.md) | Optional | The reason for not providing a VAT number.<br><br>Possible values: **industryExemption**, **belowTaxThreshold**. | getVatAbsenceReason(): ?string | setVatAbsenceReason(?string vatAbsenceReason): void |
| `vatNumber` | `?string` | Optional | The VAT number. | getVatNumber(): ?string | setVatNumber(?string vatNumber): void |

## Example

```php
use AdyenLib\Models\Builders\UnincorporatedPartnershipBuilder;
use AdyenLib\Models\Builders\Address51Builder;
use AdyenLib\Models\Builders\Address41Builder;

$unincorporatedPartnership = UnincorporatedPartnershipBuilder::init(
    'countryOfGoverningLaw6',
    'name8',
    Address51Builder::init(
        'country4'
    )
        ->city('city0')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince8')
        ->street('street0')
        ->street2('street24')
        ->build()
)
    ->dateOfIncorporation('dateOfIncorporation8')
    ->description('description8')
    ->doingBusinessAs('doingBusinessAs6')
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

