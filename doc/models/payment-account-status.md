
# Payment Account Status

## Structure

`PaymentAccountStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstrumentData` | [`?PaymentInstrumentData`](../../doc/models/payment-instrument-data.md) | Optional | Data related to the instrument of payment for the transaction.<br>Sent in the result of the payment transaction. For a card, it could also be sent in the `CardAcquisition` response, to be processed by the Sale System. | getPaymentInstrumentData(): ?PaymentInstrumentData | setPaymentInstrumentData(?PaymentInstrumentData paymentInstrumentData): void |
| `currentBalance` | `?float` | Optional | Balance of an account after processing of the transaction.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCurrentBalance(): ?float | setCurrentBalance(?float currentBalance): void |
| `currency` | `?string` | Optional | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): ?string | setCurrency(?string currency): void |
| `paymentAcquirerData` | [`?PaymentAcquirerData`](../../doc/models/payment-acquirer-data.md) | Optional | Data related to the response from the payment Acquirer. | getPaymentAcquirerData(): ?PaymentAcquirerData | setPaymentAcquirerData(?PaymentAcquirerData paymentAcquirerData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentAccountStatusBuilder;
use AdyenLib\Models\Builders\PaymentInstrumentDataBuilder;
use AdyenLib\Models\PaymentInstrumentType11Enum;
use AdyenLib\Models\Builders\CardData1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\TrackFormat1Enum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\CheckData1Builder;
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\Builders\MobileData1Builder;
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\PaymentAcquirerDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType6Builder;

$paymentAccountStatus = PaymentAccountStatusBuilder::init()
    ->paymentInstrumentData(
        PaymentInstrumentDataBuilder::init(
            PaymentInstrumentType11Enum::CASH
        )
            ->protectedCardData('ProtectedCardData8')
            ->cardData(
                CardData1Builder::init()
                    ->paymentBrand('PaymentBrand0')
                    ->maskedPan('MaskedPan0')
                    ->paymentAccountRef('PaymentAccountRef8')
                    ->entryMode(
                        [
                            EntryModeEnum::MANUAL,
                            EntryModeEnum::KEYED
                        ]
                    )
                    ->cardCountryCode(3)
                    ->build()
            )
            ->checkData(
                CheckData1Builder::init()
                    ->bankID('BankID0')
                    ->accountNumber('AccountNumber6')
                    ->checkNumber('CheckNumber2')
                    ->trackData(
                        TrackData1Builder::init(
                            'TrackValue6'
                        )
                            ->trackNumb(3)
                            ->trackFormat(TrackFormat1Enum::JISII)
                            ->build()
                    )
                    ->checkCardNumber('CheckCardNumber6')
                    ->build()
            )
            ->mobileData(
                MobileData1Builder::init()
                    ->mobileCountryCode(3)
                    ->mobileNetworkCode(3)
                    ->maskedMSISDN(22)
                    ->geolocation(
                        Geolocation1Builder::init()
                            ->geographicCoordinates(
                                GeographicCoordinatesBuilder::init(
                                    'Latitude4',
                                    'Longitude2'
                                )->build()
                            )
                            ->uTMCoordinates(
                                UTMCoordinatesBuilder::init(
                                    'UTMZone6',
                                    'UTMEastward0',
                                    'UTMNorthward0'
                                )->build()
                            )->build()
                    )
                    ->protectedMobileData('ProtectedMobileData0')
                    ->build()
            )
            ->storedValueAccountID(
                StoredValueAccountIDBuilder::init(
                    StoredValueAccountType1Enum::PHONECARD,
                    [
                        EntryModeEnum::MAGSTRIPE,
                        EntryModeEnum::SCANNED
                    ],
                    IdentificationType11Enum::PHONENUMBER,
                    'StoredValueID8'
                )
                    ->storedValueProvider('StoredValueProvider4')
                    ->ownerName('OwnerName0')
                    ->expiryDate(4)
                    ->build()
            )
            ->build()
    )
    ->currentBalance(32.76)
    ->currency('Currency0')
    ->paymentAcquirerData(
        PaymentAcquirerDataBuilder::init(
            'MerchantID6',
            'AcquirerPOIID4'
        )
            ->acquirerID(238)
            ->acquirerTransactionID(
                TransactionIDType6Builder::init(
                    'TransactionID2',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->approvalCode('ApprovalCode8')
            ->hostReconciliationID('HostReconciliationID8')
            ->build()
    )
    ->build();
```

