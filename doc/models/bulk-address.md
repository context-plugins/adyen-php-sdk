
# Bulk Address

## Structure

`BulkAddress`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The name of the city. | getCity(): ?string | setCity(?string city): void |
| `company` | `?string` | Optional | The name of the company. | getCompany(): ?string | setCompany(?string company): void |
| `country` | `string` | Required | The two-character ISO-3166-1 alpha-2 country code. For example, **US**. | getCountry(): string | setCountry(string country): void |
| `email` | `?string` | Optional | The email address. | getEmail(): ?string | setEmail(?string email): void |
| `houseNumberOrName` | `?string` | Optional | The house number or name. | getHouseNumberOrName(): ?string | setHouseNumberOrName(?string houseNumberOrName): void |
| `line1` | `?string` | Optional | The name of the street and the number of the building.<br><br>For example: **Simon Carmiggeltstraat 6-50**. | getLine1(): ?string | setLine1(?string line1): void |
| `line2` | `?string` | Optional | Additional information about the delivery address. For example, an apartment number. | getLine2(): ?string | setLine2(?string line2): void |
| `line3` | `?string` | Optional | Additional information about the delivery address. | getLine3(): ?string | setLine3(?string line3): void |
| `mobile` | `?string` | Optional | The full telephone number. | getMobile(): ?string | setMobile(?string mobile): void |
| `name` | `?string` | Optional | The recipient’s name (person or contact), for example ‘John Doe’. | getName(): ?string | setName(?string name): void |
| `postalCode` | `?string` | Optional | The postal code.<br><br>Maximum length:<br><br>* 5 digits for addresses in the US.<br><br>* 10 characters for all other countries. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `stateOrProvince` | `?string` | Optional | The two-letter ISO 3166-2 state or province code.<br><br>Maximum length: 2 characters for addresses in the US. | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |
| `street` | `?string` | Optional | The streetname of the house. | getStreet(): ?string | setStreet(?string street): void |

## Example

```php
use AdyenLib\Models\Builders\BulkAddressBuilder;

$bulkAddress = BulkAddressBuilder::init(
    'country0'
)
    ->city('city6')
    ->company('company6')
    ->email('email0')
    ->houseNumberOrName('houseNumberOrName4')
    ->line1('line18')
    ->build();
```

