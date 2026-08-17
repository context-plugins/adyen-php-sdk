
# Schedule Account Updater Result

## Structure

`ScheduleAccountUpdaterResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pspReference` | `string` | Required | Adyen's 16-character unique reference associated with the transaction. This value is globally unique; quote it when communicating with us about this request. | getPspReference(): string | setPspReference(string pspReference): void |
| `result` | `string` | Required | The result of scheduling an Account Updater. If scheduling was successful, this field returns **Success**; otherwise it contains the error message. | getResult(): string | setResult(string result): void |

## Example

```php
use AdyenLib\Models\Builders\ScheduleAccountUpdaterResultBuilder;

$scheduleAccountUpdaterResult = ScheduleAccountUpdaterResultBuilder::init(
    'pspReference8',
    'result6'
)->build();
```

