
# Capability Problem

## Structure

`CapabilityProblem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entity` | [`?CapabilityProblemEntity2`](../../doc/models/capability-problem-entity-2.md) | Optional | Contains the type of the entity and the corresponding ID. | getEntity(): ?CapabilityProblemEntity2 | setEntity(?CapabilityProblemEntity2 entity): void |
| `verificationErrors` | [`?(VerificationError[])`](../../doc/models/verification-error.md) | Optional | Contains information about the verification error. | getVerificationErrors(): ?array | setVerificationErrors(?array verificationErrors): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilityProblemBuilder;
use AdyenLib\Models\Builders\CapabilityProblemEntity2Builder;
use AdyenLib\Models\Builders\CapabilityProblemEntityRecursive2Builder;
use AdyenLib\Models\Type33Enum;
use AdyenLib\Models\Builders\VerificationErrorBuilder;
use AdyenLib\Models\CapabilityEnum;
use AdyenLib\Models\Builders\RemediatingActionBuilder;
use AdyenLib\Models\Builders\VerificationErrorRecursiveBuilder;
use AdyenLib\Models\Type212Enum;

$capabilityProblem = CapabilityProblemBuilder::init()
    ->entity(
        CapabilityProblemEntity2Builder::init()
            ->documents(
                [
                    'documents1',
                    'documents2'
                ]
            )
            ->id('id2')
            ->owner(
                CapabilityProblemEntityRecursive2Builder::init()
                    ->documents(
                        [
                            'documents3',
                            'documents4'
                        ]
                    )
                    ->id('id4')
                    ->type(Type33Enum::LEGALENTITY)
                    ->build()
            )
            ->type(Type33Enum::LEGALENTITY)
            ->build()
    )
    ->verificationErrors(
        [
            VerificationErrorBuilder::init()
                ->capabilities(
                    [
                        CapabilityEnum::USECARDINRESTRICTEDINDUSTRIESCOMMERCIAL
                    ]
                )
                ->code('code0')
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
                            ->build(),
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
                            ->build(),
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
                ->build()
        ]
    )
    ->build();
```

