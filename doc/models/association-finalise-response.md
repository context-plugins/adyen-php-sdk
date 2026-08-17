
# Association Finalise Response

## Structure

`AssociationFinaliseResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deviceId` | `?string` | Optional | The unique identifier of the SCA device you associated with a resource. | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `ids` | `?(string[])` | Optional | The list of unique identifiers of the resources that you associated with the SCA device. | getIds(): ?array | setIds(?array ids): void |
| `type` | `string` | Required, Constant | The type of resource that you associated with the SCA device.<br><br>**Value**: `'PAYMENT_INSTRUMENT'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AssociationFinaliseResponseBuilder;

$associationFinaliseResponse = AssociationFinaliseResponseBuilder::init()
    ->deviceId('deviceId4')
    ->ids(
        [
            'ids5',
            'ids6'
        ]
    )
    ->build();
```

