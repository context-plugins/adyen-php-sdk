
# Payment Methods Response

## Structure

`PaymentMethodsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentMethods` | [`?(PaymentMethod[])`](../../doc/models/payment-method.md) | Optional | Detailed list of payment methods required to generate payment forms. | getPaymentMethods(): ?array | setPaymentMethods(?array paymentMethods): void |
| `storedPaymentMethods` | [`?(StoredPaymentMethod3[])`](../../doc/models/stored-payment-method-3.md) | Optional | List of all stored payment methods. | getStoredPaymentMethods(): ?array | setStoredPaymentMethods(?array storedPaymentMethods): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentMethodsResponseBuilder;
use AdyenLib\Models\Builders\PaymentMethodBuilder;
use AdyenLib\Models\Builders\PaymentMethodUPIAppsBuilder;
use AdyenLib\Models\Builders\AppIdentifierInfo1Builder;
use AdyenLib\Models\FundingSource9Enum;
use AdyenLib\Models\Builders\StoredPaymentMethod3Builder;

$paymentMethodsResponse = PaymentMethodsResponseBuilder::init()
    ->paymentMethods(
        [
            PaymentMethodBuilder::init()
                ->apps(
                    [
                        PaymentMethodUPIAppsBuilder::init(
                            'id6',
                            'name6'
                        )
                            ->appIdentifierInfo(
                                AppIdentifierInfo1Builder::init()
                                    ->androidPackageId('androidPackageId8')
                                    ->iosScheme('iosScheme8')
                                    ->build()
                            )
                            ->build(),
                        PaymentMethodUPIAppsBuilder::init(
                            'id6',
                            'name6'
                        )
                            ->appIdentifierInfo(
                                AppIdentifierInfo1Builder::init()
                                    ->androidPackageId('androidPackageId8')
                                    ->iosScheme('iosScheme8')
                                    ->build()
                            )
                            ->build()
                    ]
                )
                ->brand('brand6')
                ->brands(
                    [
                        'brands3'
                    ]
                )
                ->configuration(
                    [
                        'key0' => 'configuration2',
                        'key1' => 'configuration1',
                        'key2' => 'configuration0'
                    ]
                )
                ->fundingSource(FundingSource9Enum::DEBIT)
                ->build()
        ]
    )
    ->storedPaymentMethods(
        [
            StoredPaymentMethod3Builder::init()
                ->bankAccountNumber('bankAccountNumber2')
                ->bankLocationId('bankLocationId6')
                ->brand('brand6')
                ->cashtag('cashtag0')
                ->expiryMonth('expiryMonth6')
                ->build(),
            StoredPaymentMethod3Builder::init()
                ->bankAccountNumber('bankAccountNumber2')
                ->bankLocationId('bankLocationId6')
                ->brand('brand6')
                ->cashtag('cashtag0')
                ->expiryMonth('expiryMonth6')
                ->build(),
            StoredPaymentMethod3Builder::init()
                ->bankAccountNumber('bankAccountNumber2')
                ->bankLocationId('bankLocationId6')
                ->brand('brand6')
                ->cashtag('cashtag0')
                ->expiryMonth('expiryMonth6')
                ->build()
        ]
    )
    ->build();
```

