
# Verification Error

## Structure

`VerificationError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`?(string(CapabilityEnum)[])`](../../doc/models/capability-enum.md) | Optional | Contains the capabilities that the verification error applies to. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `code` | `?string` | Optional | The verification error code. | getCode(): ?string | setCode(?string code): void |
| `message` | `?string` | Optional | A description of the error. | getMessage(): ?string | setMessage(?string message): void |
| `remediatingActions` | [`?(RemediatingAction[])`](../../doc/models/remediating-action.md) | Optional | Contains the actions that you can take to resolve the verification error. | getRemediatingActions(): ?array | setRemediatingActions(?array remediatingActions): void |
| `subErrors` | [`?(VerificationErrorRecursive[])`](../../doc/models/verification-error-recursive.md) | Optional | Contains more granular information about the verification error. | getSubErrors(): ?array | setSubErrors(?array subErrors): void |
| `type` | [`?string(Type212Enum)`](../../doc/models/type-212-enum.md) | Optional | The type of error.<br><br>Possible values:<br><br>* **invalidInput**<br>* **dataMissing**<br>* **pendingStatus**<br>* **dataReview** | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\VerificationErrorBuilder;
use AdyenLib\Models\CapabilityEnum;
use AdyenLib\Models\Builders\RemediatingActionBuilder;
use AdyenLib\Models\Builders\VerificationErrorRecursiveBuilder;
use AdyenLib\Models\Type212Enum;

$verificationError = VerificationErrorBuilder::init()
    ->capabilities(
        [
            CapabilityEnum::USECHARGECARDCOMMERCIAL,
            CapabilityEnum::WITHDRAWFROMATM
        ]
    )
    ->code('code2')
    ->message('message4')
    ->remediatingActions(
        [
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build(),
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build(),
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build()
        ]
    )
    ->subErrors(
        [
            VerificationErrorRecursiveBuilder::init()
                ->capabilities(
                    [
                        CapabilityEnum::PROCESSING,
                        CapabilityEnum::PAYOUTTOTRANSFERINSTRUMENT
                    ]
                )
                ->code('code2')
                ->message('message4')
                ->type(Type212Enum::INVALIDINPUT)
                ->remediatingActions(
                    [
                        RemediatingActionBuilder::init()
                            ->code('code4')
                            ->message('message6')
                            ->build(),
                        RemediatingActionBuilder::init()
                            ->code('code4')
                            ->message('message6')
                            ->build(),
                        RemediatingActionBuilder::init()
                            ->code('code4')
                            ->message('message6')
                            ->build()
                    ]
                )
                ->build()
        ]
    )
    ->build();
```

