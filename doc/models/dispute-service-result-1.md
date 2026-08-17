
# Dispute Service Result 1

The result of the dispute service.

## Structure

`DisputeServiceResult1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessage` | `?string` | Optional | The general error message. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `success` | `bool` | Required | Indicates whether the request succeeded. | getSuccess(): bool | setSuccess(bool success): void |

## Example

```php
use AdyenLib\Models\Builders\DisputeServiceResult1Builder;

$disputeServiceResult1 = DisputeServiceResult1Builder::init(
    false
)
    ->errorMessage('errorMessage8')
    ->build();
```

