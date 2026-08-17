
# Modification 2

The payment modification. Only applicable for [returned internal transfers](https://docs.adyen.com/platforms/internal-fund-transfers/internal-transfer-webhooks/#returned-internal-transfer).

## Structure

`Modification2`

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
use AdyenLib\Models\Builders\Modification2Builder;
use AdyenLib\Models\Status24Enum;

$modification2 = Modification2Builder::init()
    ->direction('direction6')
    ->id('id0')
    ->reference('reference4')
    ->status(Status24Enum::REFUNDREVERSED)
    ->type('type0')
    ->build();
```

