
# Disable Permit Request

## Structure

`DisablePermitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `token` | `string` | Required | The permit token to disable. | getToken(): string | setToken(string token): void |

## Example

```php
use AdyenLib\Models\Builders\DisablePermitRequestBuilder;

$disablePermitRequest = DisablePermitRequestBuilder::init(
    'merchantAccount8',
    'token0'
)->build();
```

