
# Ticket Response Info

## Structure

`TicketResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestorId` | `?string` | Optional | Ticket requestorId | getRequestorId(): ?string | setRequestorId(?string requestorId): void |

## Example

```php
use AdyenLib\Models\Builders\TicketResponseInfoBuilder;

$ticketResponseInfo = TicketResponseInfoBuilder::init()
    ->requestorId('requestorId4')
    ->build();
```

