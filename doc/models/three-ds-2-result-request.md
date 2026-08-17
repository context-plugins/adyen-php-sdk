
# Three DS 2 Result Request

## Structure

`ThreeDS2ResultRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `pspReference` | `string` | Required | The pspReference returned in the /authorise call. | getPspReference(): string | setPspReference(string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDS2ResultRequestBuilder;

$threeDS2ResultRequest = ThreeDS2ResultRequestBuilder::init(
    'merchantAccount0',
    'pspReference0'
)->build();
```

