
# Service Error 1

## Structure

`ServiceError1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorCode` | `?string` | Optional | The error code mapped to the error message. | getErrorCode(): ?string | setErrorCode(?string errorCode): void |
| `errorType` | `?string` | Optional | The category of the error. | getErrorType(): ?string | setErrorType(?string errorType): void |
| `message` | `?string` | Optional | A short explanation of the issue. | getMessage(): ?string | setMessage(?string message): void |
| `pspReference` | `?string` | Optional | The PSP reference of the payment. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `status` | `?int` | Optional | The HTTP response status. | getStatus(): ?int | setStatus(?int status): void |

## Example

```php
use AdyenLib\Models\Builders\ServiceError1Builder;

$serviceError1 = ServiceError1Builder::init()
    ->errorCode('errorCode2')
    ->errorType('errorType6')
    ->message('message6')
    ->pspReference('pspReference8')
    ->status(142)
    ->build();
```

