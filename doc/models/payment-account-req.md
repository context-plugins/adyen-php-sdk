
# Payment Account Req

## Structure

`PaymentAccountReq`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountType` | [`?string(AccountType12Enum)`](../../doc/models/account-type-12-enum.md) | Optional | Type of cardholder account used for the transaction. Allows a cardholder to select the type of account used for the transaction.<br>Possible values:<br><br>* **CardTotals**<br>* **Checking**<br>* **CreditCard**<br>* **Default**<br>* **EpurseCard**<br>* **Investment**<br>* **Savings**<br>* **Universal** | getAccountType(): ?string | setAccountType(?string accountType): void |
| `cardAcquisitionReference` | [`?TransactionIDType`](../../doc/models/transaction-id-type.md) | Optional | Identification of a transaction for the Sale System or the POI System. | getCardAcquisitionReference(): ?TransactionIDType | setCardAcquisitionReference(?TransactionIDType cardAcquisitionReference): void |
| `paymentInstrumentData` | [`?PaymentInstrumentData`](../../doc/models/payment-instrument-data.md) | Optional | Data related to the instrument of payment for the transaction.<br>Sent in the result of the payment transaction. For a card, it could also be sent in the `CardAcquisition` response, to be processed by the Sale System. | getPaymentInstrumentData(): ?PaymentInstrumentData | setPaymentInstrumentData(?PaymentInstrumentData paymentInstrumentData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentAccountReqBuilder;
use AdyenLib\Models\AccountType12Enum;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\PaymentInstrumentDataBuilder;
use AdyenLib\Models\PaymentInstrumentType11Enum;
use AdyenLib\Models\Builders\CardData1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\TrackFormat1Enum;
use AdyenLib\Models\Builders\CheckData1Builder;
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\Builders\MobileData1Builder;
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\IdentificationType11Enum;

$paymentAccountReq = PaymentAccountReqBuilder::init()
    ->accountType(AccountType12Enum::CARDTOTALS)
    ->cardAcquisitionReference(
        TransactionIDTypeBuilder::init(
            'TransactionID8',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
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
    ->build();
```

