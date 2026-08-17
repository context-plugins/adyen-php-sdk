
# Payment Token

Surrogate of the PAN (Primary Account Number) of the payment card to
identify the payment mean of the customer. It allows, for a merchant, to identify
the customer.

## Structure

`PaymentToken`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `tokenRequestedType` | [`string(TokenRequestedType1Enum)`](../../doc/models/token-requested-type-1-enum.md) | Required | Type of token replacing the PAN of a payment card to identify the payment<br>mean of the customer. It allows, for a merchant, to use a token for a transaction<br>only or for a longer period.<br>Possible values:<br><br>* **Customer**<br>* **Transaction** | getTokenRequestedType(): string | setTokenRequestedType(string tokenRequestedType): void |
| `tokenValue` | `string` | Required | Payment token replacing the PAN of the payment card to identify the payment<br>mean of the customer.<br><br>**Constraints**: *Pattern*: `^.+$` | getTokenValue(): string | setTokenValue(string tokenValue): void |
| `expiryDateTime` | `?DateTime` | Optional | Expiry date and time. Limits the validity of a payment token. | getExpiryDateTime(): ?\DateTime | setExpiryDateTime(?\DateTime expiryDateTime): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentTokenBuilder;
use AdyenLib\Models\TokenRequestedType1Enum;
use AdyenLib\Utils\DateTimeHelper;

$paymentToken = PaymentTokenBuilder::init(
    TokenRequestedType1Enum::TRANSACTION,
    'TokenValue8'
)
    ->expiryDateTime(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

