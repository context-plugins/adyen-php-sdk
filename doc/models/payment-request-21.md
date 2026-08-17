
# Payment Request 21

Content of the Payment Request message.

## Structure

`PaymentRequest21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleData` | [`SaleData1`](../../doc/models/sale-data-1.md) | Required | Data related to the Sale System. | getSaleData(): SaleData1 | setSaleData(SaleData1 saleData): void |
| `paymentTransaction` | [`PaymentTransaction1`](../../doc/models/payment-transaction-1.md) | Required | Data related to the payment and loyalty transaction. | getPaymentTransaction(): PaymentTransaction1 | setPaymentTransaction(PaymentTransaction1 paymentTransaction): void |
| `paymentData` | [`?PaymentData1`](../../doc/models/payment-data-1.md) | Optional | Data related to the payment transaction.<br>If one data element is present. | getPaymentData(): ?PaymentData1 | setPaymentData(?PaymentData1 paymentData): void |
| `loyaltyData` | [`?(LoyaltyData[])`](../../doc/models/loyalty-data.md) | Optional | Data related to a Loyalty program or account.<br>Loyalty cards used with the payment transaction and read by the Sale System. | getLoyaltyData(): ?array | setLoyaltyData(?array loyaltyData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentRequest21Builder;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\PaymentTransaction1Builder;
use AdyenLib\Models\Builders\AmountsReqBuilder;
use AdyenLib\Models\Builders\OriginalPOITransactionBuilder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Models\Builders\TransactionConditionsBuilder;
use AdyenLib\Models\LoyaltyHandling1Enum;
use AdyenLib\Models\Builders\PaymentData1Builder;
use AdyenLib\Models\PaymentType1Enum;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Models\Builders\Instalment1Builder;
use AdyenLib\Models\InstalmentTypeEnum;
use AdyenLib\Models\PeriodUnit1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\LoyaltyDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType3Builder;
use AdyenLib\Models\Builders\LoyaltyAccountID1Builder;
use AdyenLib\Models\IdentificationSupport1Enum;

$paymentRequest21 = PaymentRequest21Builder::init(
    SaleData1Builder::init(
        TransactionIDType1Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
        ->operatorID('OperatorID8')
        ->operatorLanguage('OperatorLanguage2')
        ->shiftNumber('ShiftNumber0')
        ->saleReferenceID('SaleReferenceID8')
        ->saleTerminalData(
            SaleTerminalData1Builder::init()
                ->totalsGroupID('TotalsGroupID4')
                ->build()
        )
        ->build(),
    PaymentTransaction1Builder::init(
        AmountsReqBuilder::init(
            'Currency4',
            38.52
        )
            ->cashBackAmount(77.72)
            ->tipAmount(40.18)
            ->paidAmount(239.98)
            ->minimumAmountToDeliver(73.38)
            ->maximumCashBackAmount(36.82)
            ->build()
    )
        ->originalPOITransaction(
            OriginalPOITransactionBuilder::init()
                ->saleID('SaleID6')
                ->pOIID('POIID0')
                ->pOITransactionID(
                    TransactionIDType4Builder::init(
                        'TransactionID2',
                        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                    )->build()
                )
                ->reuseCardDataFlag(false)
                ->approvalCode('ApprovalCode0')
                ->build()
        )
        ->transactionConditions(
            TransactionConditionsBuilder::init()
                ->allowedPaymentBrand(
                    [
                        'AllowedPaymentBrand0',
                        'AllowedPaymentBrand1',
                        'AllowedPaymentBrand2'
                    ]
                )
                ->acquirerID(
                    [
                        56,
                        57,
                        58
                    ]
                )
                ->debitPreferredFlag(false)
                ->allowedLoyaltyBrand(
                    [
                        'AllowedLoyaltyBrand8',
                        'AllowedLoyaltyBrand9'
                    ]
                )
                ->loyaltyHandling(LoyaltyHandling1Enum::FORBIDDEN)
                ->build()
        )
        ->build()
)
    ->paymentData(
        PaymentData1Builder::init()
            ->paymentType(PaymentType1Enum::NORMAL)
            ->splitPaymentFlag(false)
            ->requestedValidityDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->cardAcquisitionReference(
                TransactionIDTypeBuilder::init(
                    'TransactionID8',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->instalment(
                Instalment1Builder::init()
                    ->instalmentType(InstalmentTypeEnum::DEFERREDINSTALMENTS)
                    ->sequenceNumber(106)
                    ->planID('PlanID4')
                    ->period(70)
                    ->periodUnit(PeriodUnit1Enum::MONTHLY)
                    ->build()
            )
            ->build()
    )
    ->loyaltyData(
        [
            LoyaltyDataBuilder::init()
                ->cardAcquisitionReference(
                    TransactionIDType3Builder::init(
                        'TransactionID8',
                        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                    )->build()
                )
                ->loyaltyAccountID(
                    LoyaltyAccountID1Builder::init(
                        [
                            EntryModeEnum::FILE
                        ],
                        IdentificationType11Enum::ISOTRACK2,
                        'LoyaltyID4'
                    )
                        ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                        ->build()
                )
                ->build(),
            LoyaltyDataBuilder::init()
                ->cardAcquisitionReference(
                    TransactionIDType3Builder::init(
                        'TransactionID8',
                        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                    )->build()
                )
                ->loyaltyAccountID(
                    LoyaltyAccountID1Builder::init(
                        [
                            EntryModeEnum::FILE
                        ],
                        IdentificationType11Enum::ISOTRACK2,
                        'LoyaltyID4'
                    )
                        ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                        ->build()
                )
                ->build(),
            LoyaltyDataBuilder::init()
                ->cardAcquisitionReference(
                    TransactionIDType3Builder::init(
                        'TransactionID8',
                        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                    )->build()
                )
                ->loyaltyAccountID(
                    LoyaltyAccountID1Builder::init(
                        [
                            EntryModeEnum::FILE
                        ],
                        IdentificationType11Enum::ISOTRACK2,
                        'LoyaltyID4'
                    )
                        ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

