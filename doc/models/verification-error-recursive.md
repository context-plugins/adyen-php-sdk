
# Verification Error Recursive

## Structure

`VerificationErrorRecursive`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`?(string(CapabilityEnum)[])`](../../doc/models/capability-enum.md) | Optional | Contains the capabilities that the verification error applies to. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `code` | `?string` | Optional | The verification error code. | getCode(): ?string | setCode(?string code): void |
| `message` | `?string` | Optional | A description of the error. | getMessage(): ?string | setMessage(?string message): void |
| `type` | [`?string(Type212Enum)`](../../doc/models/type-212-enum.md) | Optional | The type of error.<br><br>Possible values:<br><br>* **invalidInput**<br>* **dataMissing**<br>* **pendingStatus**<br>* **dataReview** | getType(): ?string | setType(?string type): void |
| `remediatingActions` | [`?(RemediatingAction[])`](../../doc/models/remediating-action.md) | Optional | Contains the actions that you can take to resolve the verification error. | getRemediatingActions(): ?array | setRemediatingActions(?array remediatingActions): void |

## Example

```php
use AdyenLib\Models\Builders\VerificationErrorRecursiveBuilder;
use AdyenLib\Models\CapabilityEnum;
use AdyenLib\Models\Type212Enum;
use AdyenLib\Models\Builders\RemediatingActionBuilder;

$verificationErrorRecursive = VerificationErrorRecursiveBuilder::init()
    ->capabilities(
        [
            CapabilityEnum::USECARDINRESTRICTEDINDUSTRIES,
            CapabilityEnum::USECARDINRESTRICTEDCOUNTRIESCONSUMER
        ]
    )
    ->code('code0')
    ->message('message2')
    ->type(Type212Enum::DATAMISSING)
    ->remediatingActions(
        [
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build()
        ]
    )
    ->build();
```

