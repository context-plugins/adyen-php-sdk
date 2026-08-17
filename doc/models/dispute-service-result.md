
# Dispute Service Result

## Structure

`DisputeServiceResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorMessage` | `?string` | Optional | The general error message. | getErrorMessage(): ?string | setErrorMessage(?string errorMessage): void |
| `success` | `bool` | Required | Indicates whether the request succeeded. | getSuccess(): bool | setSuccess(bool success): void |

## Example

```php
use AdyenLib\Models\Builders\DisputeServiceResultBuilder;

$disputeServiceResult = DisputeServiceResultBuilder::init(
    false
)
    ->errorMessage('errorMessage8')
    ->build();
```

