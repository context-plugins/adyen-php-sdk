
# Un Suspend Account Holder Request

## Structure

`UnSuspendAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder to be reinstated. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |

## Example

```php
use AdyenLib\Models\Builders\UnSuspendAccountHolderRequestBuilder;

$unSuspendAccountHolderRequest = UnSuspendAccountHolderRequestBuilder::init(
    'accountHolderCode0'
)->build();
```

