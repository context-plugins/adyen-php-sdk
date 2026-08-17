
# Defense Reasons Response

## Structure

`DefenseReasonsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defenseReasons` | [`?(DefenseReason[])`](../../doc/models/defense-reason.md) | Optional | The defense reasons that can be used to defend the dispute. | getDefenseReasons(): ?array | setDefenseReasons(?array defenseReasons): void |
| `disputeServiceResult` | [`DisputeServiceResult1`](../../doc/models/dispute-service-result-1.md) | Required | The result of the dispute service. | getDisputeServiceResult(): DisputeServiceResult1 | setDisputeServiceResult(DisputeServiceResult1 disputeServiceResult): void |

## Example

```php
use AdyenLib\Models\Builders\DefenseReasonsResponseBuilder;
use AdyenLib\Models\Builders\DisputeServiceResult1Builder;
use AdyenLib\Models\Builders\DefenseReasonBuilder;
use AdyenLib\Models\Builders\DefenseDocumentTypeBuilder;

$defenseReasonsResponse = DefenseReasonsResponseBuilder::init(
    DisputeServiceResult1Builder::init(
        false
    )
        ->errorMessage('errorMessage8')
        ->build()
)
    ->defenseReasons(
        [
            DefenseReasonBuilder::init(
                'defenseReasonCode0',
                false
            )
                ->defenseDocumentTypes(
                    [
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build(),
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build()
                    ]
                )->build(),
            DefenseReasonBuilder::init(
                'defenseReasonCode0',
                false
            )
                ->defenseDocumentTypes(
                    [
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build(),
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build()
                    ]
                )->build(),
            DefenseReasonBuilder::init(
                'defenseReasonCode0',
                false
            )
                ->defenseDocumentTypes(
                    [
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build(),
                        DefenseDocumentTypeBuilder::init(
                            false,
                            'defenseDocumentTypeCode0',
                            'requirementLevel4'
                        )->build()
                    ]
                )->build()
        ]
    )->build();
```

