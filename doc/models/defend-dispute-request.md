
# Defend Dispute Request

## Structure

`DefendDisputeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defenseReasonCode` | `string` | Required | The defense reason code that was selected to defend this dispute. | getDefenseReasonCode(): string | setDefenseReasonCode(string defenseReasonCode): void |
| `disputePspReference` | `string` | Required | The PSP reference assigned to the dispute. | getDisputePspReference(): string | setDisputePspReference(string disputePspReference): void |
| `merchantAccountCode` | `string` | Required | The merchant account identifier, for which you want to process the dispute transaction. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\DefendDisputeRequestBuilder;

$defendDisputeRequest = DefendDisputeRequestBuilder::init(
    'defenseReasonCode2',
    'disputePspReference0',
    'merchantAccountCode2'
)->build();
```

