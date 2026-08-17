
# Verification Error 1

## Structure

`VerificationError1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`?(string(CapabilityEnum)[])`](../../doc/models/capability-enum.md) | Optional | Contains key-value pairs that specify the actions that the legal entity can do in your platform. The key is a capability required for your integration. For example, **issueCard** for Issuing.The value is an object containing the settings for the capability. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `code` | `?string` | Optional | The general error code. | getCode(): ?string | setCode(?string code): void |
| `message` | `?string` | Optional | The general error message. | getMessage(): ?string | setMessage(?string message): void |
| `remediatingActions` | [`?(RemediatingAction[])`](../../doc/models/remediating-action.md) | Optional | An object containing possible solutions to fix a verification error. | getRemediatingActions(): ?array | setRemediatingActions(?array remediatingActions): void |
| `subErrors` | [`?(VerificationErrorRecursive1[])`](../../doc/models/verification-error-recursive-1.md) | Optional | An array containing more granular information about the cause of the verification error. | getSubErrors(): ?array | setSubErrors(?array subErrors): void |
| `type` | [`?string(Type512Enum)`](../../doc/models/type-512-enum.md) | Optional | The type of error.<br><br>Possible values:<br><br>* **invalidInput**<br>* **dataMissing**<br>* **pendingStatus**<br>* **rejected**<br>* **dataReview** | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\VerificationError1Builder;
use AdyenLib\Models\CapabilityEnum;
use AdyenLib\Models\Builders\RemediatingActionBuilder;
use AdyenLib\Models\Builders\VerificationErrorRecursive1Builder;
use AdyenLib\Models\Type512Enum;

$verificationError1 = VerificationError1Builder::init()
    ->capabilities(
        [
            CapabilityEnum::ATMWITHDRAWALINRESTRICTEDCOUNTRIESCONSUMER
        ]
    )
    ->code('code6')
    ->message('message8')
    ->remediatingActions(
        [
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
            VerificationErrorRecursive1Builder::init()
                ->capabilities(
                    [
                        CapabilityEnum::PROCESSING,
                        CapabilityEnum::PAYOUTTOTRANSFERINSTRUMENT
                    ]
                )
                ->code('code2')
                ->message('message4')
                ->type(Type512Enum::DATAREVIEW)
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
                ->build(),
            VerificationErrorRecursive1Builder::init()
                ->capabilities(
                    [
                        CapabilityEnum::PROCESSING,
                        CapabilityEnum::PAYOUTTOTRANSFERINSTRUMENT
                    ]
                )
                ->code('code2')
                ->message('message4')
                ->type(Type512Enum::DATAREVIEW)
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
                ->build(),
            VerificationErrorRecursive1Builder::init()
                ->capabilities(
                    [
                        CapabilityEnum::PROCESSING,
                        CapabilityEnum::PAYOUTTOTRANSFERINSTRUMENT
                    ]
                )
                ->code('code2')
                ->message('message4')
                ->type(Type512Enum::DATAREVIEW)
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

