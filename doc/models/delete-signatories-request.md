
# Delete Signatories Request

## Structure

`DeleteSignatoriesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder from which to delete the signatories. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `signatoryCodes` | `string[]` | Required | Array of codes of the signatories to be deleted. | getSignatoryCodes(): array | setSignatoryCodes(array signatoryCodes): void |

## Example

```php
use AdyenLib\Models\Builders\DeleteSignatoriesRequestBuilder;

$deleteSignatoriesRequest = DeleteSignatoriesRequestBuilder::init(
    'accountHolderCode2',
    [
        'signatoryCodes3'
    ]
)->build();
```

