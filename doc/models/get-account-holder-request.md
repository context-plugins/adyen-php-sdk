
# Get Account Holder Request

## Structure

`GetAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The code of the account of which to retrieve the details.<br><br>> Required if no `accountHolderCode` is provided. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `accountHolderCode` | `?string` | Optional | The code of the account holder of which to retrieve the details.<br><br>> Required if no `accountCode` is provided. | getAccountHolderCode(): ?string | setAccountHolderCode(?string accountHolderCode): void |
| `showDetails` | `?bool` | Optional | True if the request should return the account holder details | getShowDetails(): ?bool | setShowDetails(?bool showDetails): void |

## Example

```php
use AdyenLib\Models\Builders\GetAccountHolderRequestBuilder;

$getAccountHolderRequest = GetAccountHolderRequestBuilder::init()
    ->accountCode('accountCode2')
    ->accountHolderCode('accountHolderCode6')
    ->showDetails(false)
    ->build();
```

