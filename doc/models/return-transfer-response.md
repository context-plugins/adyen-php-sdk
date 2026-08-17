
# Return Transfer Response

## Structure

`ReturnTransferResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the return. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | Your internal reference for the return. | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status62Enum)`](../../doc/models/status-62-enum.md) | Optional | The resulting status of the return.<br><br>Possible values: **Authorised**, **Declined**. | getStatus(): ?string | setStatus(?string status): void |
| `transferId` | `?string` | Optional | The unique identifier of the original transfer. | getTransferId(): ?string | setTransferId(?string transferId): void |

## Example

```php
use AdyenLib\Models\Builders\ReturnTransferResponseBuilder;
use AdyenLib\Models\Status62Enum;

$returnTransferResponse = ReturnTransferResponseBuilder::init()
    ->id('id8')
    ->reference('reference4')
    ->status(Status62Enum::AUTHORISED)
    ->transferId('transferId6')
    ->build();
```

