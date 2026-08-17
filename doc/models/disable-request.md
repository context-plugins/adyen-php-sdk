
# Disable Request

## Structure

`DisableRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `contract` | `?string` | Optional | Specify the contract if you only want to disable a specific use.<br><br>This field can be set to one of the following values, or to their combination (comma-separated):<br><br>* ONECLICK<br>* RECURRING<br>* PAYOUT | getContract(): ?string | setContract(?string contract): void |
| `merchantAccount` | `string` | Required | The merchant account identifier with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `recurringDetailReference` | `?string` | Optional | The ID that uniquely identifies the recurring detail reference.<br><br>If it is not provided, the whole recurring contract of the `shopperReference` will be disabled, which includes all recurring details. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `shopperReference` | `string` | Required | The ID that uniquely identifies the shopper.<br><br>This `shopperReference` must be the same as the `shopperReference` used in the initial payment. | getShopperReference(): string | setShopperReference(string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\DisableRequestBuilder;

$disableRequest = DisableRequestBuilder::init(
    'merchantAccount4',
    'shopperReference2'
)
    ->contract('contract4')
    ->recurringDetailReference('recurringDetailReference4')
    ->build();
```

