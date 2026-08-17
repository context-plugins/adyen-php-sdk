
# Sca Entity

## Structure

`ScaEntity`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `100` | getId(): string | setId(string id): void |
| `type` | [`string(ScaEntityType4Enum)`](../../doc/models/sca-entity-type-4-enum.md) | Required | The type of the entity that you are associating with the SCA device.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\ScaEntityBuilder;
use AdyenLib\Models\ScaEntityType4Enum;

$scaEntity = ScaEntityBuilder::init(
    'AH9999Z99Z999999ZZZZ9999Z',
    ScaEntityType4Enum::ACCOUNTHOLDER
)->build();
```

