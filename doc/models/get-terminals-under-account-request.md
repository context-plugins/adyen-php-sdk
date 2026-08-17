
# Get Terminals Under Account Request

## Structure

`GetTerminalsUnderAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyAccount` | `string` | Required | Your company account. If you only specify this parameter, the response includes all terminals at all account levels. | getCompanyAccount(): string | setCompanyAccount(string companyAccount): void |
| `merchantAccount` | `?string` | Optional | The merchant account. This is required if you are retrieving the terminals assigned to a store.If you don't specify a `store` the response includes the terminals assigned to the specified merchant account and the terminals assigned to the stores under this merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `store` | `?string` | Optional | The store code of the store. With this parameter, the response only includes the terminals assigned to the specified store. | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\GetTerminalsUnderAccountRequestBuilder;

$getTerminalsUnderAccountRequest = GetTerminalsUnderAccountRequestBuilder::init(
    'companyAccount0'
)
    ->merchantAccount('merchantAccount2')
    ->store('store4')
    ->build();
```

