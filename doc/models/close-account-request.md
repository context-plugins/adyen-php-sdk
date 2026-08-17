
# Close Account Request

## Structure

`CloseAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of account to be closed. | getAccountCode(): string | setAccountCode(string accountCode): void |

## Example

```php
use AdyenLib\Models\Builders\CloseAccountRequestBuilder;

$closeAccountRequest = CloseAccountRequestBuilder::init(
    'accountCode6'
)->build();
```

