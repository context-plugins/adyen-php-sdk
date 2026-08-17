
# Ticket Info

## Structure

`TicketInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestorId` | `?string` | Optional | Ticket requestorId | getRequestorId(): ?string | setRequestorId(?string requestorId): void |

## Example

```php
use AdyenLib\Models\Builders\TicketInfoBuilder;

$ticketInfo = TicketInfoBuilder::init()
    ->requestorId('requestorId6')
    ->build();
```

