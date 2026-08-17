
# US Ach Tracing Data

## Structure

`USAchTracingData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `traceNumber` | `string` | Required | The ACH trace number. This is a unique 15-digit identifier assigned to transfers processed by [ACH](https://fiscal.treasury.gov/payments-from-government/automated-clearing-house-ach). | getTraceNumber(): string | setTraceNumber(string traceNumber): void |
| `type` | `string` | Required, Constant | **usAch**<br><br>**Value**: `'usAch'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\USAchTracingDataBuilder;

$uSAchTracingData = USAchTracingDataBuilder::init(
    'traceNumber2'
)->build();
```

