
# Balance Inquiry Request 2

Content of the Balance Inquiry Request message.

## Structure

`BalanceInquiryRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentAccountReq` | [`?PaymentAccountReq2`](../../doc/models/payment-account-req-2.md) | Optional | Data related to the account pointed by the payment card. | getPaymentAccountReq(): ?PaymentAccountReq2 | setPaymentAccountReq(?PaymentAccountReq2 paymentAccountReq): void |
| `loyaltyAccountReq` | [`?LoyaltyAccountReq2`](../../doc/models/loyalty-account-req-2.md) | Optional | Data related to a requested Loyalty program or account. | getLoyaltyAccountReq(): ?LoyaltyAccountReq2 | setLoyaltyAccountReq(?LoyaltyAccountReq2 loyaltyAccountReq): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceInquiryRequest2Builder;
use AdyenLib\Models\Builders\PaymentAccountReq2Builder;
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
use AdyenLib\Models\Builders\LoyaltyAccountReq2Builder;
use AdyenLib\Models\Builders\LoyaltyAccountIDBuilder;
use AdyenLib\Models\IdentificationSupport1Enum;

$balanceInquiryRequest2 = BalanceInquiryRequest2Builder::init()
    ->paymentAccountReq(
        PaymentAccountReq2Builder::init()
            ->accountType(AccountType12Enum::CHECKING)
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
            ->build()
    )
    ->loyaltyAccountReq(
        LoyaltyAccountReq2Builder::init()
            ->cardAcquisitionReference(
                TransactionIDTypeBuilder::init(
                    'TransactionID8',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->loyaltyAccountID(
                LoyaltyAccountIDBuilder::init(
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
    )
    ->build();
```

