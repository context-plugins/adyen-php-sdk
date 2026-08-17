
# Ticket Info 2

Details to provide if `type` is **ticket** (Edenred Brazil).

## Structure

`TicketInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestorId` | `?string` | Optional | Ticket requestorId | getRequestorId(): ?string | setRequestorId(?string requestorId): void |

## Example

```php
use AdyenLib\Models\Builders\TicketInfo2Builder;

$ticketInfo2 = TicketInfo2Builder::init()
    ->requestorId('requestorId8')
    ->build();
```

