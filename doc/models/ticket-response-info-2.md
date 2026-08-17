
# Ticket Response Info 2

**ticket** (Edenred Brazil) details

## Structure

`TicketResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestorId` | `?string` | Optional | Ticket requestorId | getRequestorId(): ?string | setRequestorId(?string requestorId): void |

## Example

```php
use AdyenLib\Models\Builders\TicketResponseInfo2Builder;

$ticketResponseInfo2 = TicketResponseInfo2Builder::init()
    ->requestorId('requestorId0')
    ->build();
```

