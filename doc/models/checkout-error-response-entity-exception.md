
# Checkout Error Response Entity Exception

## Structure

`CheckoutErrorResponseEntityException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorCode` | `string` | Required | - | getErrorCode(): string | setErrorCode(string errorCode): void |
| `errorType` | `string` | Required | - | getErrorType(): string | setErrorType(string errorType): void |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |
| `pspReference` | `?string` | Optional | - | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `status` | `?int` | Optional | - | getStatus(): ?int | setStatus(?int status): void |

## Example

```php
try {
    // make the API call
} catch (CheckoutErrorResponseEntityException $exp) {
    echo 'Caught CheckoutErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

