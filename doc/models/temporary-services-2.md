
# Temporary Services 2

[Temporary services enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/temporary-services/) that may be required for processing the transaction and/or for interchange savings.

## Structure

`TemporaryServices2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `employeeName` | `?string` | Optional | The name or ID of the person working in a temporary capacity.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `enhancedSchemeData.employeeName` | getEmployeeName(): ?string | setEmployeeName(?string employeeName): void |
| `endDate` | `?DateTime` | Optional | The billing period end date.<br><br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `enhancedSchemeData.tempWeekEnding` | getEndDate(): ?\DateTime | setEndDate(?\DateTime endDate): void |
| `hourRate` | `?int` | Optional | The hourly rate for the temporary services, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `enhancedSchemeData.regularHoursRate` | getHourRate(): ?int | setHourRate(?int hourRate): void |
| `hoursWorked` | `?int` | Optional | The number of hours worked during the billing period.<br><br>* Format: Numeric<br>* **additionalData key:** `enhancedSchemeData.regularHoursWorked` | getHoursWorked(): ?int | setHoursWorked(?int hoursWorked): void |
| `jobDescription` | `?string` | Optional | The job description of the person working in a temporary capacity.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `enhancedSchemeData.jobDescription` | getJobDescription(): ?string | setJobDescription(?string jobDescription): void |
| `serviceRequestor` | `?string` | Optional | The name of the person requesting the temporary services.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `enhancedSchemeData.requestName` | getServiceRequestor(): ?string | setServiceRequestor(?string serviceRequestor): void |
| `startDate` | `?DateTime` | Optional | The billing period start date.<br><br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `enhancedSchemeData.tempStartDate` | getStartDate(): ?\DateTime | setStartDate(?\DateTime startDate): void |

## Example

```php
use AdyenLib\Models\Builders\TemporaryServices2Builder;
use AdyenLib\Utils\DateTimeHelper;

$temporaryServices2 = TemporaryServices2Builder::init()
    ->employeeName('employeeName4')
    ->endDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->hourRate(14)
    ->hoursWorked(182)
    ->jobDescription('jobDescription4')
    ->build();
```

