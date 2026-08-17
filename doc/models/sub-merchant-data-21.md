
# Sub Merchant Data 21

The details of the sub-merchant that you want to process transactions for.Required if you are a registered payment facilitator. Do not include this parameter if you are not a payment facilitator.

## Structure

`SubMerchantData21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The city of the sub-merchant's address. | getCity(): ?string | setCity(?string city): void |
| `country` | `?string` | Optional | The country/region of the sub-merchant's address, specified as the three-letter country code in [ISO 3166-1 alpha-3](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3) format. | getCountry(): ?string | setCountry(?string country): void |
| `displayName` | `string` | Required | The name of the sub-merchant as it should appear on the display of the mobile device during transactions. | getDisplayName(): string | setDisplayName(string displayName): void |
| `email` | `?string` | Optional | The email address of the sub-merchant. Required for American Express. | getEmail(): ?string | setEmail(?string email): void |
| `id` | `string` | Required | Your unique identifier of the sub-merchant. | getId(): string | setId(string id): void |
| `mcc` | `string` | Required | The sub-merchant's four-digit Merchant Category Code (MCC). This parameter is used to correctly route the transaction. | getMcc(): string | setMcc(string mcc): void |
| `name` | `string` | Required | The name of the sub-merchant. | getName(): string | setName(string name): void |
| `phoneNumber` | `?string` | Optional | The phone number of the sub-merchant. Required for American Express. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `postalCode` | `?string` | Optional | The postal code of the sub-merchant's address, without dashes. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `state` | `?string` | Optional | The state code of the sub-merchant's address, if applicable for the country or region. | getState(): ?string | setState(?string state): void |
| `street` | `?string` | Optional | The street name and house number of the sub-merchant's address. | getStreet(): ?string | setStreet(?string street): void |
| `taxId` | `?string` | Optional | The tax ID of the sub-merchant. Required only in Brazil and for Cartes Bancaires in France.<br>For Brazil, this is the 11-digit CPF or 14-digit CNPJ.<br>For France, this is the SIRET, with a maximum of 14 digits. | getTaxId(): ?string | setTaxId(?string taxId): void |

## Example

```php
use AdyenLib\Models\Builders\SubMerchantData21Builder;

$subMerchantData21 = SubMerchantData21Builder::init(
    'displayName6',
    'id8',
    'mcc8',
    'name8'
)
    ->city('city8')
    ->country('country2')
    ->email('email8')
    ->phoneNumber('phoneNumber8')
    ->postalCode('postalCode0')
    ->build();
```

