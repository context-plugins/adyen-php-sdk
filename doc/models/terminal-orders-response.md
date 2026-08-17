
# Terminal Orders Response

## Structure

`TerminalOrdersResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(TerminalOrder[])`](../../doc/models/terminal-order.md) | Optional | List of orders for payment terminal packages and parts. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalOrdersResponseBuilder;
use AdyenLib\Models\Builders\TerminalOrderBuilder;
use AdyenLib\Models\Builders\BillingEntity1Builder;
use AdyenLib\Models\Builders\Address11Builder;
use AdyenLib\Models\Builders\OrderItemBuilder;

$terminalOrdersResponse = TerminalOrdersResponseBuilder::init()
    ->data(
        [
            TerminalOrderBuilder::init()
                ->billingEntity(
                    BillingEntity1Builder::init()
                        ->address(
                            Address11Builder::init()
                                ->city('city6')
                                ->companyName('companyName8')
                                ->country('country0')
                                ->postalCode('postalCode8')
                                ->stateOrProvince('stateOrProvince4')
                                ->build()
                        )
                        ->email('email0')
                        ->id('id6')
                        ->name('name6')
                        ->taxId('taxId2')
                        ->build()
                )
                ->customerOrderReference('customerOrderReference2')
                ->id('id0')
                ->items(
                    [
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build(),
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build(),
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build()
                    ]
                )
                ->orderDate('orderDate0')
                ->build(),
            TerminalOrderBuilder::init()
                ->billingEntity(
                    BillingEntity1Builder::init()
                        ->address(
                            Address11Builder::init()
                                ->city('city6')
                                ->companyName('companyName8')
                                ->country('country0')
                                ->postalCode('postalCode8')
                                ->stateOrProvince('stateOrProvince4')
                                ->build()
                        )
                        ->email('email0')
                        ->id('id6')
                        ->name('name6')
                        ->taxId('taxId2')
                        ->build()
                )
                ->customerOrderReference('customerOrderReference2')
                ->id('id0')
                ->items(
                    [
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build(),
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build(),
                        OrderItemBuilder::init()
                            ->id('id8')
                            ->installments(204)
                            ->name('name8')
                            ->quantity(22)
                            ->build()
                    ]
                )
                ->orderDate('orderDate0')
                ->build()
        ]
    )
    ->build();
```

