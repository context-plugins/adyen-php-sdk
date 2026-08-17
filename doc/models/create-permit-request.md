
# Create Permit Request

## Structure

`CreatePermitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `permits` | [`Permit[]`](../../doc/models/permit.md) | Required | The permits to create for this recurring contract. | getPermits(): array | setPermits(array permits): void |
| `recurringDetailReference` | `string` | Required | The recurring contract the new permits will use. | getRecurringDetailReference(): string | setRecurringDetailReference(string recurringDetailReference): void |
| `shopperReference` | `string` | Required | The shopper's reference to uniquely identify this shopper (e.g. user ID or account ID). | getShopperReference(): string | setShopperReference(string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\CreatePermitRequestBuilder;
use AdyenLib\Models\Builders\PermitBuilder;
use AdyenLib\Models\Builders\PermitRestriction2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Utils\DateTimeHelper;

$createPermitRequest = CreatePermitRequestBuilder::init(
    'merchantAccount4',
    [
        PermitBuilder::init()
            ->partnerId('partnerId8')
            ->profileReference('profileReference0')
            ->restriction(
                PermitRestriction2Builder::init()
                    ->maxAmount(
                        AmountBuilder::init(
                            'currency4',
                            160
                        )->build()
                    )
                    ->singleTransactionLimit(
                        AmountBuilder::init(
                            'currency8',
                            122
                        )->build()
                    )
                    ->singleUse(false)
                    ->build()
            )
            ->resultKey('resultKey4')
            ->validTillDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->build()
    ],
    'recurringDetailReference2',
    'shopperReference0'
)->build();
```

