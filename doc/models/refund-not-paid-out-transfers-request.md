
# Refund Not Paid Out Transfers Request

## Structure

`RefundNotPaidOutTransfersRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of the account from which to perform the refund(s). | getAccountCode(): string | setAccountCode(string accountCode): void |
| `accountHolderCode` | `string` | Required | The code of the Account Holder which owns the account from which to perform the refund(s). | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |

## Example

```php
use AdyenLib\Models\Builders\RefundNotPaidOutTransfersRequestBuilder;

$refundNotPaidOutTransfersRequest = RefundNotPaidOutTransfersRequestBuilder::init(
    'accountCode4',
    'accountHolderCode0'
)->build();
```

