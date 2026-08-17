
# List Nonprofits Request

## Structure

`ListNonprofitsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderIds` | `string[]` | Required | The unique identifiers of the account holders to be included in a donation campaign.<br><br>**Constraints**: *Minimum Items*: `1` | getAccountHolderIds(): array | setAccountHolderIds(array accountHolderIds): void |

## Example

```php
use AdyenLib\Models\Builders\ListNonprofitsRequestBuilder;

$listNonprofitsRequest = ListNonprofitsRequestBuilder::init(
    [
        'accountHolderIds7',
        'accountHolderIds8'
    ]
)->build();
```

