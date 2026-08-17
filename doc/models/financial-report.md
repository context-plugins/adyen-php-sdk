
# Financial Report

## Structure

`FinancialReport`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `annualTurnover` | `?string` | Optional | The annual turnover of the business. | getAnnualTurnover(): ?string | setAnnualTurnover(?string annualTurnover): void |
| `balanceSheetTotal` | `?string` | Optional | The balance sheet total of the business. | getBalanceSheetTotal(): ?string | setBalanceSheetTotal(?string balanceSheetTotal): void |
| `currencyOfFinancialData` | `?string` | Optional | The currency used for the annual turnover, balance sheet total, and net assets. | getCurrencyOfFinancialData(): ?string | setCurrencyOfFinancialData(?string currencyOfFinancialData): void |
| `dateOfFinancialData` | `?string` | Optional | The date the financial data were provided, in YYYY-MM-DD format. | getDateOfFinancialData(): ?string | setDateOfFinancialData(?string dateOfFinancialData): void |
| `employeeCount` | `?string` | Optional | The number of employees of the business. | getEmployeeCount(): ?string | setEmployeeCount(?string employeeCount): void |
| `netAssets` | `?string` | Optional | The net assets of the business. | getNetAssets(): ?string | setNetAssets(?string netAssets): void |

## Example

```php
use AdyenLib\Models\Builders\FinancialReportBuilder;

$financialReport = FinancialReportBuilder::init()
    ->annualTurnover('annualTurnover6')
    ->balanceSheetTotal('balanceSheetTotal4')
    ->currencyOfFinancialData('currencyOfFinancialData6')
    ->dateOfFinancialData('dateOfFinancialData0')
    ->employeeCount('employeeCount0')
    ->build();
```

