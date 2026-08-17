
# Payment Result 1

## Structure

`PaymentResult1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?string(PaymentType1Enum)`](../../doc/models/payment-type-1-enum.md) | Optional | Type of payment transaction. Elements requested by the Sale System that are related to the payment only.<br>Possible values:<br><br>* **CashAdvance**<br>* **CashDeposit**<br>* **Completion**<br>* **FirstReservation**<br>* **Instalment**<br>* **IssuerInstalment**<br>* **Normal**<br>* **OneTimeReservation**<br>* **PaidOut**<br>* **Recurring**<br>* **Refund**<br>* **UpdateReservation** | getPaymentType(): ?string | setPaymentType(?string paymentType): void |
| `paymentInstrumentData` | [`?PaymentInstrumentData`](../../doc/models/payment-instrument-data.md) | Optional | Data related to the instrument of payment for the transaction.<br>Sent in the result of the payment transaction. For a card, it could also be sent in the `CardAcquisition` response, to be processed by the Sale System. | getPaymentInstrumentData(): ?PaymentInstrumentData | setPaymentInstrumentData(?PaymentInstrumentData paymentInstrumentData): void |
| `amountsResp` | [`?AmountsResp1`](../../doc/models/amounts-resp-1.md) | Optional | Various amounts related to the payment response from the POI System. Amounts approved by the POI and the Acquirer for the payment and loyalty transaction, containing:<br><br>* The authorised amount to be paid.<br>* The amount of the rebates.<br>* The amount of financial fees.<br>* The cash back part of the requested amount for a payment with cash back.<br>* The tip part of the requested amount for a payment with tip. | getAmountsResp(): ?AmountsResp1 | setAmountsResp(?AmountsResp1 amountsResp): void |
| `instalment` | [`?Instalment1`](../../doc/models/instalment-1.md) | Optional | Information related an instalment transaction. To request an instalment to the issuer, or to make individual instalments of a payment transaction. | getInstalment(): ?Instalment1 | setInstalment(?Instalment1 instalment): void |
| `currencyConversion` | [`?(CurrencyConversion[])`](../../doc/models/currency-conversion.md) | Optional | Information related to a currency conversion. A currency conversion occurred in the payment, and the merchant needs to know information related to this conversion (e.g. to print on the sale receipt). | getCurrencyConversion(): ?array | setCurrencyConversion(?array currencyConversion): void |
| `merchantOverrideFlag` | `?bool` | Optional | Indicates that the Merchant forced the result of the payment to successful. Allows the Sale System to be sure that the payment has been forced.<br><br>**Default**: `false` | getMerchantOverrideFlag(): ?bool | setMerchantOverrideFlag(?bool merchantOverrideFlag): void |
| `capturedSignature` | [`?CapturedSignature1`](../../doc/models/captured-signature-1.md) | Optional | Numeric value of a handwritten signature. Contains the value of a handwritten signature, e.g. the signature of a cardholder on the merchant payment receipt. Only one format of the signature is allowed:<br><br>* The size of the pad area where the signature is written, given with the maximum abscissa and ordinate values.<br>* The sequence of coordinates where the pen changes direction or lift. | getCapturedSignature(): ?CapturedSignature1 | setCapturedSignature(?CapturedSignature1 capturedSignature): void |
| `protectedSignature` | `?string` | Optional | Numeric value of a handwritten signature. Contains the value of a handwritten signature, e.g. the signature of a cardholder on the merchant payment receipt. The format before encryption is the encoded data structure CapturedSignature. The data structure before encryption includes the start and end tags for an XML encoding, the identifier and length bytes for an ASN.1 encoding, and the complete member ProtectedSignature for a JSON encoding. | getProtectedSignature(): ?string | setProtectedSignature(?string protectedSignature): void |
| `customerLanguage` | `?string` | Optional | The language of the customer that was used on the terminal screen or in text printed by the terminal. Format: two-character [ISO 639:2023](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) format.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getCustomerLanguage(): ?string | setCustomerLanguage(?string customerLanguage): void |
| `onlineFlag` | `?bool` | Optional | Indicate that the payment transaction processing has required the approval of a host. Allows the Sale System to know if the payment was online or offline.<br><br>**Default**: `true` | getOnlineFlag(): ?bool | setOnlineFlag(?bool onlineFlag): void |
| `authenticationMethod` | [`?(string(AuthenticationMethod1Enum)[])`](../../doc/models/authentication-method-1-enum.md) | Optional | Method for customer authentication. Allows the Sale System informed about customer authentication for the payment transaction.<br>Possible values:<br><br>* **Bypass**<br>* **ManualVerification**<br>* **MerchantAuthentication**<br>* **OfflinePIN**<br>* **OnlinePIN**<br>* **PaperSignature**<br>* **SecureCertificate**<br>* **SecureNoCertificate**<br>* **SecuredChannel**<br>* **SignatureCapture**<br>* **UnknownMethod** | getAuthenticationMethod(): ?array | setAuthenticationMethod(?array authenticationMethod): void |
| `validityDate` | `?DateTime` | Optional | End of the validity period for the reservation, for the first reservation, and the reservation updates as well. | getValidityDate(): ?\DateTime | setValidityDate(?\DateTime validityDate): void |
| `paymentAcquirerData` | [`?PaymentAcquirerData`](../../doc/models/payment-acquirer-data.md) | Optional | Data related to the response from the payment Acquirer. | getPaymentAcquirerData(): ?PaymentAcquirerData | setPaymentAcquirerData(?PaymentAcquirerData paymentAcquirerData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentResult1Builder;
use AdyenLib\Models\PaymentType1Enum;
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
use AdyenLib\Models\Builders\AmountsResp1Builder;
use AdyenLib\Models\Builders\Instalment1Builder;
use AdyenLib\Models\InstalmentTypeEnum;
use AdyenLib\Models\PeriodUnit1Enum;
use AdyenLib\Models\Builders\CurrencyConversionBuilder;
use AdyenLib\Models\Builders\ConvertedAmount1Builder;

$paymentResult1 = PaymentResult1Builder::init()
    ->paymentType(PaymentType1Enum::ISSUERINSTALMENT)
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
    ->amountsResp(
        AmountsResp1Builder::init(
            133.28
        )
            ->currency('Currency0')
            ->totalRebatesAmount(120.04)
            ->totalFeesAmount(181.08)
            ->cashBackAmount(206.58)
            ->tipAmount(86.96)
            ->build()
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
    ->currencyConversion(
        [
            CurrencyConversionBuilder::init(
                ConvertedAmount1Builder::init(
                    81.82,
                    'Currency0'
                )->build()
            )
                ->customerApprovedFlag(false)
                ->rate(175.8)
                ->markup(100.86)
                ->commission(197.78)
                ->declaration('Declaration4')
                ->build(),
            CurrencyConversionBuilder::init(
                ConvertedAmount1Builder::init(
                    81.82,
                    'Currency0'
                )->build()
            )
                ->customerApprovedFlag(false)
                ->rate(175.8)
                ->markup(100.86)
                ->commission(197.78)
                ->declaration('Declaration4')
                ->build()
        ]
    )
    ->merchantOverrideFlag(false)
    ->onlineFlag(true)
    ->build();
```

