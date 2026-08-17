
# We Chat Pay Info 2

Details to provide if `type` is **wechatpay**.

## Structure

`WeChatPayInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contactPersonName` | `string` | Required | The name of the contact person from merchant support. | getContactPersonName(): string | setContactPersonName(string contactPersonName): void |
| `email` | `string` | Required | The email address of merchant support. | getEmail(): string | setEmail(string email): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayInfo2Builder;

$weChatPayInfo2 = WeChatPayInfo2Builder::init(
    'contactPersonName0',
    'email0'
)->build();
```

