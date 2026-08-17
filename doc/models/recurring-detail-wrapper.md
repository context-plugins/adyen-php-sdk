
# Recurring Detail Wrapper

## Structure

`RecurringDetailWrapper`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `recurringDetail` | [`?RecurringDetail`](../../doc/models/recurring-detail.md) | Optional | - | getRecurringDetail(): ?RecurringDetail | setRecurringDetail(?RecurringDetail recurringDetail): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringDetailWrapperBuilder;
use AdyenLib\Models\Builders\RecurringDetailBuilder;
use AdyenLib\Models\Builders\BankAccountBuilder;
use AdyenLib\Models\Builders\AddressBuilder;

$recurringDetailWrapper = RecurringDetailWrapperBuilder::init()
    ->recurringDetail(
        RecurringDetailBuilder::init(
            'recurringDetailReference2',
            'variant6'
        )
            ->additionalData(
                [
                    'key0' => 'additionalData2'
                ]
            )
            ->alias('alias4')
            ->aliasType('aliasType6')
            ->bank(
                BankAccountBuilder::init()
                    ->bankAccountNumber('bankAccountNumber8')
                    ->bankCity('bankCity0')
                    ->bankLocationId('bankLocationId2')
                    ->bankName('bankName4')
                    ->bic('bic0')
                    ->build()
            )
            ->billingAddress(
                AddressBuilder::init(
                    'city8',
                    'country6',
                    'houseNumberOrName0',
                    'postalCode6',
                    'street2'
                )
                    ->stateOrProvince('stateOrProvince0')
                    ->build()
            )
            ->build()
    )
    ->build();
```

