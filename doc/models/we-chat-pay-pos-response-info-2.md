
# We Chat Pay Pos Response Info 2

**wechatpay_pos** details

## Structure

`WeChatPayPosResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contactPersonName` | `?string` | Optional | The name of the contact person from merchant support. | getContactPersonName(): ?string | setContactPersonName(?string contactPersonName): void |
| `email` | `?string` | Optional | The email address of merchant support. | getEmail(): ?string | setEmail(?string email): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayPosResponseInfo2Builder;

$weChatPayPosResponseInfo2 = WeChatPayPosResponseInfo2Builder::init()
    ->contactPersonName('contactPersonName8')
    ->email('email2')
    ->build();
```

