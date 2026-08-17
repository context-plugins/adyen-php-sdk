
# Target 3

The resource about whose balance change you want to get notified.

## Structure

`Target3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The unique identifier of the `target.type`. This can be the ID of your:<br><br>* balance platform<br>* account holder<br>* account holder's balance account<br><br>**Constraints**: *Minimum Length*: `1` | getId(): string | setId(string id): void |
| `type` | [`string(Type181Enum)`](../../doc/models/type-181-enum.md) | Required | The resource for which you want to receive notifications. Possible values:<br><br>* **balancePlatform**: receive notifications about balance changes in your entire balance platform.<br><br>* **accountHolder**: receive notifications about balance changes of a specific user.<br><br>* **balanceAccount**: receive notifications about balance changes in a specific balance account. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\Target3Builder;
use AdyenLib\Models\Type181Enum;

$target3 = Target3Builder::init(
    'id4',
    Type181Enum::BALANCEPLATFORM
)->build();
```

