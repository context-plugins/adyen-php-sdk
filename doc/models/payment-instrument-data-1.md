
# Payment Instrument Data 1

Data related to the instrument of payment for the transaction.
If this type of payment card is configured to send information if the CardAcquisition response.

## Structure

`PaymentInstrumentData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstrumentType` | [`string(PaymentInstrumentType11Enum)`](../../doc/models/payment-instrument-type-11-enum.md) | Required | Type of payment instrument.<br>Possible values:<br><br>* **Card**<br>* **Cash**<br>* **Check**<br>* **Mobile**<br>* **StoredValue** | getPaymentInstrumentType(): string | setPaymentInstrumentType(string paymentInstrumentType): void |
| `protectedCardData` | `?string` | Optional | Sensitive information related to the payment card, protected by CMS.<br>SensitiveCardData protected by CMS EnvelopedData. | getProtectedCardData(): ?string | setProtectedCardData(?string protectedCardData): void |
| `cardData` | [`?CardData1`](../../doc/models/card-data-1.md) | Optional | Information related to the payment card used for the transaction.<br>If PaymentInstrumentType is Card. | getCardData(): ?CardData1 | setCardData(?CardData1 cardData): void |
| `checkData` | [`?CheckData1`](../../doc/models/check-data-1.md) | Optional | Information related to the paper check used for the transaction.<br>If PaymentInstrumentType is Check. | getCheckData(): ?CheckData1 | setCheckData(?CheckData1 checkData): void |
| `mobileData` | [`?MobileData1`](../../doc/models/mobile-data-1.md) | Optional | Information related to the mobile for the payment transaction.<br>If PaymentInstrumentType is Mobile. | getMobileData(): ?MobileData1 | setMobileData(?MobileData1 mobileData): void |
| `storedValueAccountID` | [`?StoredValueAccountID`](../../doc/models/stored-value-account-id.md) | Optional | Identification of the stored value account or the stored value card and the associated product sold by the Sale System for stored value requests. | getStoredValueAccountID(): ?StoredValueAccountID | setStoredValueAccountID(?StoredValueAccountID storedValueAccountID): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentData1Builder;
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

$paymentInstrumentData1 = PaymentInstrumentData1Builder::init(
    PaymentInstrumentType11Enum::CHECK
)
    ->protectedCardData('ProtectedCardData6')
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
    ->build();
```

