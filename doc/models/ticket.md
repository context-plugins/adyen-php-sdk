
# Ticket

## Structure

`Ticket`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `issueAddress` | `?string` | Optional | The address of the organization that issued the ticket.<br><br>* minLength: 0 characters<br>* maxLength: 16 characters<br>* **additionalData key:** `airline.ticket_issue_address` | getIssueAddress(): ?string | setIssueAddress(?string issueAddress): void |
| `issueDate` | `?DateTime` | Optional | The date that the ticket was issued to the passenger.<br><br>* minLength: 10 characters<br>* maxLength: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `airline.issue_date` | getIssueDate(): ?\DateTime | setIssueDate(?\DateTime issueDate): void |
| `number` | `?string` | Optional | The ticket's unique identifier.<br><br>* minLength: 1 character<br>* maxLength: 15 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `airline.ticket_number` | getNumber(): ?string | setNumber(?string number): void |

## Example

```php
use AdyenLib\Models\Builders\TicketBuilder;
use AdyenLib\Utils\DateTimeHelper;

$ticket = TicketBuilder::init()
    ->issueAddress('issueAddress8')
    ->issueDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->number('number8')
    ->build();
```

