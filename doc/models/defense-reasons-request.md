
# Defense Reasons Request

## Structure

`DefenseReasonsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disputePspReference` | `string` | Required | The PSP reference assigned to the dispute. | getDisputePspReference(): string | setDisputePspReference(string disputePspReference): void |
| `merchantAccountCode` | `string` | Required | The merchant account identifier, for which you want to process the dispute transaction. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\DefenseReasonsRequestBuilder;

$defenseReasonsRequest = DefenseReasonsRequestBuilder::init(
    'disputePspReference8',
    'merchantAccountCode0'
)->build();
```

