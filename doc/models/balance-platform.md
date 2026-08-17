
# Balance Platform

## Structure

`BalancePlatform`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Your description of the balance platform.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `id` | `string` | Required | The unique identifier of the balance platform. | getId(): string | setId(string id): void |
| `status` | `?string` | Optional | The status of the balance platform.<br><br>Possible values: **Active**, **Inactive**, **Closed**, **Suspended**. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\BalancePlatformBuilder;

$balancePlatform = BalancePlatformBuilder::init(
    'id2'
)
    ->description('description2')
    ->status('status4')
    ->build();
```

