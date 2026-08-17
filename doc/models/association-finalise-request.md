
# Association Finalise Request

## Structure

`AssociationFinaliseRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ids` | `string[]` | Required | The list of unique identifiers of the resources that you are associating with the SCA device.<br><br>Maximum: 5 strings. | getIds(): array | setIds(array ids): void |
| `strongCustomerAuthentication` | [`AssociationDelegatedAuthenticationData1`](../../doc/models/association-delegated-authentication-data-1.md) | Required | Contains authentication information required to associate the resource with the SCA device. | getStrongCustomerAuthentication(): AssociationDelegatedAuthenticationData1 | setStrongCustomerAuthentication(AssociationDelegatedAuthenticationData1 strongCustomerAuthentication): void |
| `type` | `string` | Required, Constant | The type of resource that you are associating with the SCA device.<br><br>Possible value: **PaymentInstrument**<br><br>**Value**: `'PaymentInstrument'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationFinaliseRequestBuilder;
use AdyenLib\Models\Builders\AssociationDelegatedAuthenticationData1Builder;

$associationFinaliseRequest = AssociationFinaliseRequestBuilder::init(
    [
        'ids5',
        'ids6',
        'ids7'
    ],
    AssociationDelegatedAuthenticationData1Builder::init(
        'sdkOutput4'
    )->build()
)->build();
```

