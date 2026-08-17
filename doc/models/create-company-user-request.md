
# Create Company User Request

## Structure

`CreateCompanyUserRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountGroups` | `?(string[])` | Optional | The list of [account groups](https://docs.adyen.com/account/account-structure#account-groups) associated with this user. | getAccountGroups(): ?array | setAccountGroups(?array accountGroups): void |
| `associatedMerchantAccounts` | `?(string[])` | Optional | The list of [merchant accounts](https://docs.adyen.com/account/account-structure#merchant-accounts) associated with this user. | getAssociatedMerchantAccounts(): ?array | setAssociatedMerchantAccounts(?array associatedMerchantAccounts): void |
| `email` | `string` | Required | The email address of the user. | getEmail(): string | setEmail(string email): void |
| `loginMethod` | `?string` | Optional | The requested login method for the user. To use SSO, you must already have SSO configured with Adyen before creating the user.<br><br>Possible values: **Email** or **SSO** | getLoginMethod(): ?string | setLoginMethod(?string loginMethod): void |
| `name` | [`Name`](../../doc/models/name.md) | Required | The user's full name.<br><br>Allowed length: 1—80 characters. | getName(): Name | setName(Name name): void |
| `roles` | `?(string[])` | Optional | The list of [roles](https://docs.adyen.com/account/user-roles) for this user. | getRoles(): ?array | setRoles(?array roles): void |
| `timeZoneCode` | `?string` | Optional | The [tz database name](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) of the time zone of the user. For example, **Europe/Amsterdam**. | getTimeZoneCode(): ?string | setTimeZoneCode(?string timeZoneCode): void |
| `username` | `string` | Required | The user's email address that will be their username. Must be the same as the one in the `email` field.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getUsername(): string | setUsername(string username): void |

## Example

```php
use AdyenLib\Models\Builders\CreateCompanyUserRequestBuilder;
use AdyenLib\Models\Builders\NameBuilder;

$createCompanyUserRequest = CreateCompanyUserRequestBuilder::init(
    'email4',
    NameBuilder::init(
        'firstName4',
        'lastName4'
    )->build(),
    'username8'
)
    ->accountGroups(
        [
            'accountGroups7'
        ]
    )
    ->associatedMerchantAccounts(
        [
            'associatedMerchantAccounts2',
            'associatedMerchantAccounts3',
            'associatedMerchantAccounts4'
        ]
    )
    ->loginMethod('loginMethod4')
    ->roles(
        [
            'roles4'
        ]
    )
    ->timeZoneCode('timeZoneCode4')
    ->build();
```

