
# Authentication Result Request

## Structure

`AuthenticationResultRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which the authentication was processed. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `pspReference` | `string` | Required | The pspReference identifier for the transaction. | getPspReference(): string | setPspReference(string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationResultRequestBuilder;

$authenticationResultRequest = AuthenticationResultRequestBuilder::init(
    'merchantAccount2',
    'pspReference2'
)->build();
```

