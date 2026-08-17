
# Android App Error

## Structure

`AndroidAppError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorCode` | `?string` | Optional | The error code of the Android app with the `status` of either **error** or **invalid**. | getErrorCode(): ?string | setErrorCode(?string errorCode): void |
| `terminalModels` | `?(string[])` | Optional | The list of payment terminal models to which the returned `errorCode` applies. | getTerminalModels(): ?array | setTerminalModels(?array terminalModels): void |

## Example

```php
use AdyenLib\Models\Builders\AndroidAppErrorBuilder;

$androidAppError = AndroidAppErrorBuilder::init()
    ->errorCode('errorCode0')
    ->terminalModels(
        [
            'terminalModels7',
            'terminalModels8',
            'terminalModels9'
        ]
    )
    ->build();
```

