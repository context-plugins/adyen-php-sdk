
# Recurring Details Request

## Structure

`RecurringDetailsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier you want to process the (transaction) request with. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `recurring` | [`?Recurring`](../../doc/models/recurring.md) | Optional | A container for the type of a recurring contract to be retrieved.<br><br>The contract value needs to match the contract value submitted in the payment transaction used to create a recurring contract.<br>However, if `ONECLICK,RECURRING` is the original contract definition in the initial payment, then `contract` should take either `ONECLICK` or `RECURRING`, depending on whether or not you want the shopper to enter their card's security code when they finalize their purchase. | getRecurring(): ?Recurring | setRecurring(?Recurring recurring): void |
| `shopperReference` | `string` | Required | The reference you use to uniquely identify the shopper (e.g. user ID or account ID). | getShopperReference(): string | setShopperReference(string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringDetailsRequestBuilder;
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TokenServiceEnum;

$recurringDetailsRequest = RecurringDetailsRequestBuilder::init(
    'merchantAccount6',
    'shopperReference2'
)
    ->recurring(
        RecurringBuilder::init()
            ->contract(ContractEnum::ENUM_ONECLICKRECURRING)
            ->recurringDetailName('recurringDetailName2')
            ->recurringExpiry(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->recurringFrequency('recurringFrequency0')
            ->tokenService(TokenServiceEnum::VISATOKENSERVICE)
            ->build()
    )
    ->build();
```

