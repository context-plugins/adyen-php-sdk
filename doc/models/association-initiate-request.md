
# Association Initiate Request

## Structure

`AssociationInitiateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ids` | `string[]` | Required | The list of unique identifiers of the resources that you are associating with the SCA device.<br><br>Maximum: 5 strings. | getIds(): array | setIds(array ids): void |
| `type` | `string` | Required, Constant | The type of resource that you are associating with the SCA device.<br><br>Possible value: **PaymentInstrument**<br><br>**Value**: `'PaymentInstrument'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationInitiateRequestBuilder;

$associationInitiateRequest = AssociationInitiateRequestBuilder::init(
    [
        'ids3'
    ]
)->build();
```

