
# Company 1

Information regarding the company.

## Structure

`Company1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `homepage` | `?string` | Optional | The company website's home page. | getHomepage(): ?string | setHomepage(?string homepage): void |
| `name` | `?string` | Optional | The company name. | getName(): ?string | setName(?string name): void |
| `registrationNumber` | `?string` | Optional | Registration number of the company. | getRegistrationNumber(): ?string | setRegistrationNumber(?string registrationNumber): void |
| `registryLocation` | `?string` | Optional | Registry location of the company. | getRegistryLocation(): ?string | setRegistryLocation(?string registryLocation): void |
| `taxId` | `?string` | Optional | Tax ID of the company. | getTaxId(): ?string | setTaxId(?string taxId): void |
| `type` | `?string` | Optional | The company type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\Company1Builder;

$company1 = Company1Builder::init()
    ->homepage('homepage4')
    ->name('name8')
    ->registrationNumber('registrationNumber6')
    ->registryLocation('registryLocation0')
    ->taxId('taxId4')
    ->build();
```

