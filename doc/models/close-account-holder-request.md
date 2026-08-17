
# Close Account Holder Request

## Structure

`CloseAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder to be closed. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |

## Example

```php
use AdyenLib\Models\Builders\CloseAccountHolderRequestBuilder;

$closeAccountHolderRequest = CloseAccountHolderRequestBuilder::init(
    'accountHolderCode6'
)->build();
```

