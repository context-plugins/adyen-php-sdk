
# Supply Defense Document Response

## Structure

`SupplyDefenseDocumentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disputeServiceResult` | [`DisputeServiceResult1`](../../doc/models/dispute-service-result-1.md) | Required | The result of the dispute service. | getDisputeServiceResult(): DisputeServiceResult1 | setDisputeServiceResult(DisputeServiceResult1 disputeServiceResult): void |

## Example

```php
use AdyenLib\Models\Builders\SupplyDefenseDocumentResponseBuilder;
use AdyenLib\Models\Builders\DisputeServiceResult1Builder;

$supplyDefenseDocumentResponse = SupplyDefenseDocumentResponseBuilder::init(
    DisputeServiceResult1Builder::init(
        false
    )
        ->errorMessage('errorMessage8')
        ->build()
)->build();
```

