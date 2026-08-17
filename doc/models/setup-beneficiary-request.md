
# Setup Beneficiary Request

## Structure

`SetupBeneficiaryRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `destinationAccountCode` | `string` | Required | The destination account code. | getDestinationAccountCode(): string | setDestinationAccountCode(string destinationAccountCode): void |
| `merchantReference` | `?string` | Optional | A value that can be supplied at the discretion of the executing user. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `sourceAccountCode` | `string` | Required | The benefactor account. | getSourceAccountCode(): string | setSourceAccountCode(string sourceAccountCode): void |

## Example

```php
use AdyenLib\Models\Builders\SetupBeneficiaryRequestBuilder;

$setupBeneficiaryRequest = SetupBeneficiaryRequestBuilder::init(
    'destinationAccountCode4',
    'sourceAccountCode4'
)
    ->merchantReference('merchantReference4')
    ->build();
```

