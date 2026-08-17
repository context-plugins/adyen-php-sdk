
# Default Error Response Entity Exception

Standardized error response following RFC-7807 format

Find out more here: [https://www.rfc-editor.org/rfc/rfc7807](https://www.rfc-editor.org/rfc/rfc7807)

## Structure

`DefaultErrorResponseEntityException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | A human-readable explanation specific to this occurrence of the problem. | getDetail(): ?string | setDetail(?string detail): void |
| `errorCode` | `?string` | Optional | Unique business error code. | getErrorCode(): ?string | setErrorCode(?string errorCode): void |
| `instance` | `?string` | Optional | A URI that identifies the specific occurrence of the problem if applicable. | getInstance(): ?string | setInstance(?string instance): void |
| `invalidFields` | [`?(InvalidField[])`](../../doc/models/invalid-field.md) | Optional | Array of fields with validation errors when applicable. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `requestId` | `?string` | Optional | The unique reference for the request. | getRequestId(): ?string | setRequestId(?string requestId): void |
| `status` | `?int` | Optional | The HTTP status code. | getStatus(): ?int | setStatus(?int status): void |
| `title` | `?string` | Optional | A short, human-readable summary of the problem type. | getTitle(): ?string | setTitle(?string title): void |
| `type` | `?string` | Optional | A URI that identifies the validation error type. It points to human-readable documentation for the problem type. | getType(): ?string | setType(?string type): void |

## Example

```php
try {
    // make the API call
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

