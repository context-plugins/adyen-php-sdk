
# Payment Validations Name Result Raw Response

## Structure

`PaymentValidationsNameResultRawResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | The raw first name validation result that Adyen received from the scheme. First name validation result is only returned for Visa. | getFirstName(): ?string | setFirstName(?string firstName): void |
| `fullName` | `?string` | Optional | The raw full name validation result that Adyen received from the scheme. Full name is the only field that is validated for Mastercard | getFullName(): ?string | setFullName(?string fullName): void |
| `lastName` | `?string` | Optional | The raw last name validation result that Adyen received from the scheme. Last name validation result is only returned for Visa. | getLastName(): ?string | setLastName(?string lastName): void |
| `middleName` | `?string` | Optional | The raw middle name validation result that Adyen received from the scheme. Middle name validation result is only returned for Visa. | getMiddleName(): ?string | setMiddleName(?string middleName): void |
| `status` | `?string` | Optional | The raw name validation status value that Adyen received from the scheme. Only returned for Visa. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentValidationsNameResultRawResponseBuilder;

$paymentValidationsNameResultRawResponse = PaymentValidationsNameResultRawResponseBuilder::init()
    ->firstName('firstName6')
    ->fullName('fullName2')
    ->lastName('lastName2')
    ->middleName('middleName6')
    ->status('status0')
    ->build();
```

