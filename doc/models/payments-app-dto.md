
# Payments App Dto

## Structure

`PaymentsAppDto`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `installationId` | `string` | Required | The unique identifier of the Payments App instance. | getInstallationId(): string | setInstallationId(string installationId): void |
| `merchantAccountCode` | `string` | Required | The account code associated with the Payments App instance. | getMerchantAccountCode(): string | setMerchantAccountCode(string merchantAccountCode): void |
| `merchantStoreCode` | `?string` | Optional | The store code associated with the Payments App instance. | getMerchantStoreCode(): ?string | setMerchantStoreCode(?string merchantStoreCode): void |
| `status` | `string` | Required | The status of the Payments App instance. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentsAppDtoBuilder;

$paymentsAppDto = PaymentsAppDtoBuilder::init(
    'installationId6',
    'merchantAccountCode2',
    'status2'
)
    ->merchantStoreCode('merchantStoreCode8')
    ->build();
```

