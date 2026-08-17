
# Subject Erasure by Psp Reference Request

## Structure

`SubjectErasureByPspReferenceRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `forceErasure` | `?bool` | Optional | Set this to **true** if you want to delete shopper-related data, even if the shopper has an existing recurring transaction. This only deletes the shopper-related data for the specific payment, but does not cancel the existing recurring transaction. | getForceErasure(): ?bool | setForceErasure(?bool forceErasure): void |
| `merchantAccount` | `?string` | Optional | Your merchant account | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `pspReference` | `?string` | Optional | The PSP reference of the payment. We will delete all shopper-related data for this payment. | getPspReference(): ?string | setPspReference(?string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\SubjectErasureByPspReferenceRequestBuilder;

$subjectErasureByPspReferenceRequest = SubjectErasureByPspReferenceRequestBuilder::init()
    ->forceErasure(false)
    ->merchantAccount('merchantAccount8')
    ->pspReference('pspReference2')
    ->build();
```

