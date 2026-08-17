
# Payments App Response

## Structure

`PaymentsAppResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentsApps` | [`PaymentsAppDto[]`](../../doc/models/payments-app-dto.md) | Required | List of Payments Apps. | getPaymentsApps(): array | setPaymentsApps(array paymentsApps): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentsAppResponseBuilder;
use AdyenLib\Models\Builders\PaymentsAppDtoBuilder;

$paymentsAppResponse = PaymentsAppResponseBuilder::init(
    [
        PaymentsAppDtoBuilder::init(
            'installationId8',
            'merchantAccountCode4',
            'status4'
        )
            ->merchantStoreCode('merchantStoreCode4')
            ->build()
    ]
)->build();
```

