
# Get Stores Under Account Request

## Structure

`GetStoresUnderAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyAccount` | `string` | Required | The company account. If you only specify this parameter, the response includes the stores of all merchant accounts that are associated with the company account. | getCompanyAccount(): string | setCompanyAccount(string companyAccount): void |
| `merchantAccount` | `?string` | Optional | The merchant account. With this parameter, the response only includes the stores of the specified merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |

## Example

```php
use AdyenLib\Models\Builders\GetStoresUnderAccountRequestBuilder;

$getStoresUnderAccountRequest = GetStoresUnderAccountRequestBuilder::init(
    'companyAccount2'
)
    ->merchantAccount('merchantAccount0')
    ->build();
```

