
# Suspend Account Holder Request

## Structure

`SuspendAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder to be suspended. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |

## Example

```php
use AdyenLib\Models\Builders\SuspendAccountHolderRequestBuilder;

$suspendAccountHolderRequest = SuspendAccountHolderRequestBuilder::init(
    'accountHolderCode0'
)->build();
```

