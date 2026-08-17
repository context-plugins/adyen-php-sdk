
# Submit Sca Association Request

## Structure

`SubmitScaAssociationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entities` | [`ScaEntity[]`](../../doc/models/sca-entity.md) | Required | The list of entities to be associated.<br><br>**Constraints**: *Minimum Items*: `0`, *Maximum Items*: `5` | getEntities(): array | setEntities(array entities): void |

## Example

```php
use AdyenLib\Models\Builders\SubmitScaAssociationRequestBuilder;
use AdyenLib\Models\Builders\ScaEntityBuilder;
use AdyenLib\Models\ScaEntityType4Enum;

$submitScaAssociationRequest = SubmitScaAssociationRequestBuilder::init(
    [
        ScaEntityBuilder::init(
            'AH9999Z99Z999999ZZZZ9999Z',
            ScaEntityType4Enum::ACCOUNTHOLDER
        )->build()
    ]
)->build();
```

