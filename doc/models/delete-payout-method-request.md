
# Delete Payout Method Request

## Structure

`DeletePayoutMethodRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder, from which to delete the payout methods. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `payoutMethodCodes` | `string[]` | Required | The codes of the payout methods to be deleted. | getPayoutMethodCodes(): array | setPayoutMethodCodes(array payoutMethodCodes): void |

## Example

```php
use AdyenLib\Models\Builders\DeletePayoutMethodRequestBuilder;

$deletePayoutMethodRequest = DeletePayoutMethodRequestBuilder::init(
    'accountHolderCode2',
    [
        'payoutMethodCodes2',
        'payoutMethodCodes3',
        'payoutMethodCodes4'
    ]
)->build();
```

