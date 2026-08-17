
# We Chat Pay Info

## Structure

`WeChatPayInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contactPersonName` | `string` | Required | The name of the contact person from merchant support. | getContactPersonName(): string | setContactPersonName(string contactPersonName): void |
| `email` | `string` | Required | The email address of merchant support. | getEmail(): string | setEmail(string email): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayInfoBuilder;

$weChatPayInfo = WeChatPayInfoBuilder::init(
    'contactPersonName8',
    'email2'
)->build();
```

