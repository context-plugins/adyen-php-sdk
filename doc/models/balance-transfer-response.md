
# Balance Transfer Response

## Structure

`BalanceTransferResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `DateTime` | Required | The date when the balance transfer was performed. | getCreatedAt(): \DateTime | setCreatedAt(\DateTime createdAt): void |
| `pspReference` | `string` | Required | Adyen's 16-character string reference associated with the balance transfer. | getPspReference(): string | setPspReference(string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceTransferResponseBuilder;
use AdyenLib\Utils\DateTimeHelper;

$balanceTransferResponse = BalanceTransferResponseBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    'pspReference6'
)->build();
```

