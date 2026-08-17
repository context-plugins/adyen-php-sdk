
# Accept Dispute Request

## Structure

`AcceptDisputeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disputePspReference` | `string` | Required | The PSP reference assigned to the dispute. | getDisputePspReference(): string | setDisputePspReference(string disputePspReference): void |
| `merchantAccountCode` | `string` | Required | The merchant account identifier, for which you want to process the dispute transaction. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\AcceptDisputeRequestBuilder;

$acceptDisputeRequest = AcceptDisputeRequestBuilder::init(
    'disputePspReference2',
    'merchantAccountCode4'
)->build();
```

