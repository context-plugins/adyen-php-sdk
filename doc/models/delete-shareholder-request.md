
# Delete Shareholder Request

## Structure

`DeleteShareholderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder from which to delete the Shareholders. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `shareholderCodes` | `string[]` | Required | The code(s) of the Shareholders to be deleted. | getShareholderCodes(): array | setShareholderCodes(array shareholderCodes): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteShareholderRequestBuilder;

$deleteShareholderRequest = DeleteShareholderRequestBuilder::init(
    'accountHolderCode4',
    [
        'shareholderCodes5',
        'shareholderCodes6'
    ]
)->build();
```

