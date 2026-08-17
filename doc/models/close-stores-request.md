
# Close Stores Request

## Structure

`CloseStoresRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `stores` | `string[]` | Required | List of stores to be closed. | getStores(): array | setStores(array stores): void |

## Example

```php
use AdyenLib\Models\Builders\CloseStoresRequestBuilder;

$closeStoresRequest = CloseStoresRequestBuilder::init(
    'accountHolderCode2',
    [
        'stores3',
        'stores2',
        'stores1'
    ]
)->build();
```

