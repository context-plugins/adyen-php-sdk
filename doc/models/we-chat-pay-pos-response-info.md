
# We Chat Pay Pos Response Info

## Structure

`WeChatPayPosResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contactPersonName` | `?string` | Optional | The name of the contact person from merchant support. | getContactPersonName(): ?string | setContactPersonName(?string contactPersonName): void |
| `email` | `?string` | Optional | The email address of merchant support. | getEmail(): ?string | setEmail(?string email): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayPosResponseInfoBuilder;

$weChatPayPosResponseInfo = WeChatPayPosResponseInfoBuilder::init()
    ->contactPersonName('contactPersonName6')
    ->email('email4')
    ->build();
```

