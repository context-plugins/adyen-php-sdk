
# Get Tax Form Request

## Structure

`GetTaxFormRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The account holder code you provided when you created the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `formType` | `string` | Required | Type of the requested tax form. For example, 1099-K. | getFormType(): string | setFormType(string formType): void |
| `year` | `int` | Required | Applicable tax year in the YYYY format. | getYear(): int | setYear(int year): void |

## Example

```php
use AdyenLib\Models\Builders\GetTaxFormRequestBuilder;

$getTaxFormRequest = GetTaxFormRequestBuilder::init(
    'accountHolderCode6',
    'formType4',
    242
)->build();
```

