
# Additional Data Modifications

## Structure

`AdditionalDataModifications`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `installmentPaymentDataSelectedInstallmentOption` | `?string` | Optional | This is the installment option selected by the shopper. It is required only if specified by the user. | getInstallmentPaymentDataSelectedInstallmentOption(): ?string | setInstallmentPaymentDataSelectedInstallmentOption(?string installmentPaymentDataSelectedInstallmentOption): void |

## Example

```php
use AdyenLib\Models\Builders\AdditionalDataModificationsBuilder;

$additionalDataModifications = AdditionalDataModificationsBuilder::init()
    ->installmentPaymentDataSelectedInstallmentOption('installmentPaymentData.selectedInstallmentOption2')
    ->build();
```

