
# Modification

## Structure

`Modification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `direction` | `?string` | Optional | The direction of the money movement. | getDirection(): ?string | setDirection(?string direction): void |
| `id` | `?string` | Optional | Our reference for the modification. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | Your reference for the modification, used internally within your platform. | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status24Enum)`](../../doc/models/status-24-enum.md) | Optional | The status of the transfer event. | getStatus(): ?string | setStatus(?string status): void |
| `type` | `?string` | Optional | The type of transfer modification. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\ModificationBuilder;
use AdyenLib\Models\Status24Enum;

$modification = ModificationBuilder::init()
    ->direction('direction8')
    ->id('id2')
    ->reference('reference2')
    ->status(Status24Enum::DEPOSITCORRECTION)
    ->type('type8')
    ->build();
```

