
# Recurring Details Result

## Structure

`RecurringDetailsResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creationDate` | `?DateTime` | Optional | The date when the recurring details were created. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `details` | [`?(RecurringDetailWrapper[])`](../../doc/models/recurring-detail-wrapper.md) | Optional | Payment details stored for recurring payments. | getDetails(): ?array | setDetails(?array details): void |
| `lastKnownShopperEmail` | `?string` | Optional | The most recent email for this shopper (if available). | getLastKnownShopperEmail(): ?string | setLastKnownShopperEmail(?string lastKnownShopperEmail): void |
| `shopperReference` | `?string` | Optional | The reference you use to uniquely identify the shopper (e.g. user ID or account ID). | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\RecurringDetailsResultBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\RecurringDetailWrapperBuilder;
use AdyenLib\Models\Builders\RecurringDetailBuilder;
use AdyenLib\Models\Builders\BankAccountBuilder;
use AdyenLib\Models\Builders\AddressBuilder;

$recurringDetailsResult = RecurringDetailsResultBuilder::init()
    ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->details(
        [
            RecurringDetailWrapperBuilder::init()
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
                ->build()
        ]
    )
    ->lastKnownShopperEmail('lastKnownShopperEmail0')
    ->shopperReference('shopperReference8')
    ->build();
```

