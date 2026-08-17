
# Party Identification

## Structure

`PartyIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?Address12`](../../doc/models/address-12.md) | Optional | The address of the bank account or card owner. | getAddress(): ?Address12 | setAddress(?Address12 address): void |
| `dateOfBirth` | `?DateTime` | Optional | The date of birth of the individual in [ISO-8601](https://www.w3.org/TR/NOTE-datetime) format. For example, **YYYY-MM-DD**.<br><br>Allowed only when `type` is **individual**. | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `email` | `?string` | Optional | The email address of the organization or individual. Maximum length: 254 characters.<br><br>**Constraints**: *Maximum Length*: `254` | getEmail(): ?string | setEmail(?string email): void |
| `firstName` | `?string` | Optional | The first name of the individual.<br><br>Supported characters: [a-z] [A-Z] - . / — and space.<br><br>This parameter is:<br><br>- Allowed only when `type` is **individual**.<br>- Required when `category` is **card**. | getFirstName(): ?string | setFirstName(?string firstName): void |
| `fullName` | `?string` | Optional | The full name of the entity that owns the bank account or card.<br><br>Supported characters: [a-z] [A-Z] [0-9] , . ; : - — / \ + & ! ? @ ( ) " ' and space.<br><br>Required when `category` is **bank**. | getFullName(): ?string | setFullName(?string fullName): void |
| `lastName` | `?string` | Optional | The last name of the individual.<br><br>Supported characters: [a-z] [A-Z] - . / — and space.<br><br>This parameter is:<br><br>- Allowed only when `type` is **individual**.<br>- Required when `category` is **card**. | getLastName(): ?string | setLastName(?string lastName): void |
| `reference` | `?string` | Optional | A unique reference to identify the party or counterparty involved in the transfer. For example, your client's unique wallet or payee ID.<br><br>Required when you include `cardIdentification.storedPaymentMethodId`.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `type` | [`?string(Type112Enum)`](../../doc/models/type-112-enum.md) | Optional | The type of entity that owns the bank account or card.<br><br>Possible values: **individual**, **organization**, or **unknown**.<br><br>Required when `category` is **card**. In this case, the value must be **individual**.<br><br>**Default**: `Type112Enum::UNKNOWN` | getType(): ?string | setType(?string type): void |
| `url` | `?string` | Optional | The URL of the organization or individual. Maximum length: 255 characters.<br><br>**Constraints**: *Maximum Length*: `255` | getUrl(): ?string | setUrl(?string url): void |

## Example

```php
use AdyenLib\Models\Builders\PartyIdentificationBuilder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Type112Enum;

$partyIdentification = PartyIdentificationBuilder::init()
    ->address(
        Address12Builder::init(
            'country0'
        )
            ->city('city6')
            ->line1('line18')
            ->line2('line20')
            ->postalCode('postalCode8')
            ->stateOrProvince('stateOrProvince4')
            ->build()
    )
    ->dateOfBirth(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->email('email0')
    ->firstName('firstName8')
    ->fullName('fullName6')
    ->type(Type112Enum::UNKNOWN)
    ->build();
```

