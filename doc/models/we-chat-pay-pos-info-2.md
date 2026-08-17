
# We Chat Pay Pos Info 2

Details to provide if `type` is **wechatpay_pos**.

## Structure

`WeChatPayPosInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contactPersonName` | `string` | Required | The name of the contact person from merchant support. | getContactPersonName(): string | setContactPersonName(string contactPersonName): void |
| `email` | `string` | Required | The email address of merchant support. | getEmail(): string | setEmail(string email): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayPosInfo2Builder;

$weChatPayPosInfo2 = WeChatPayPosInfo2Builder::init(
    'contactPersonName6',
    'email4'
)->build();
```

