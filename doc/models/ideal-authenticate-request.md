
# Ideal Authenticate Request

## Structure

`IdealAuthenticateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier for an account holder.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `150` | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `payload` | `string` | Required | A payload provided by iDEAL to complete the authentication process.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `400` | getPayload(): string | setPayload(string payload): void |

## Example

```php
use AdyenLib\Models\Builders\IdealAuthenticateRequestBuilder;

$idealAuthenticateRequest = IdealAuthenticateRequestBuilder::init(
    'AH00000000000000000000000',
    'https://ideal.auth/somePayload'
)->build();
```

