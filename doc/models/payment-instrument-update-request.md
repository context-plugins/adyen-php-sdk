
# Payment Instrument Update Request

## Structure

`PaymentInstrumentUpdateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the balance account associated with this payment instrument.<br><br>> You can only change the balance account ID if the payment instrument has **inactive** status. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `card` | [`?CardInfo2`](../../doc/models/card-info-2.md) | Optional | Object that contains information about the card payment instrument. | getCard(): ?CardInfo2 | setCard(?CardInfo2 card): void |
| `status` | [`?string(Status10Enum)`](../../doc/models/status-10-enum.md) | Optional | The status of the payment instrument. If a status is not specified when creating a payment instrument, it is set to **active** by default. However, there can be exceptions for cards based on the `card.formFactor` and the `issuingCountryCode`. For example, when issuing physical cards in the US, the default status is **inactive**.<br><br>Possible values:<br><br>* **active**:  The payment instrument is active and can be used to make payments.<br><br>* **inactive**: The payment instrument is inactive and cannot be used to make payments.<br><br>* **suspended**: The payment instrument is suspended, either because it was stolen or lost.<br><br>* **closed**: The payment instrument is permanently closed. This action cannot be undone. | getStatus(): ?string | setStatus(?string status): void |
| `statusComment` | `?string` | Optional | Comment for the status of the payment instrument.<br><br>Required if `statusReason` is **other**. | getStatusComment(): ?string | setStatusComment(?string statusComment): void |
| `statusReason` | [`?string(StatusReason2Enum)`](../../doc/models/status-reason-2-enum.md) | Optional | The reason for updating the status of the payment instrument.<br><br>Possible values: **lost**, **stolen**, **damaged**, **suspectedFraud**, **expired**, **endOfLife**, **accountClosure**, **other**.<br>If the reason is **other**, you must also send the `statusComment` parameter describing the status change. | getStatusReason(): ?string | setStatusReason(?string statusReason): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentUpdateRequestBuilder;
use AdyenLib\Models\Builders\CardInfo2Builder;
use AdyenLib\Models\FormFactor1Enum;
use AdyenLib\Models\Builders\Authentication1Builder;
use AdyenLib\Models\Builders\Phone11Builder;
use AdyenLib\Models\Type410Enum;
use AdyenLib\Models\Builders\CardConfiguration2Builder;
use AdyenLib\Models\Builders\BulkAddress1Builder;
use AdyenLib\Models\Builders\DeliveryContact1Builder;
use AdyenLib\Models\Builders\StoreLocationBuilder;
use AdyenLib\Models\Builders\NameBuilder;
use AdyenLib\Models\Builders\ViasPhoneNumberBuilder;
use AdyenLib\Models\PhoneTypeEnum;
use AdyenLib\Models\Status10Enum;
use AdyenLib\Models\StatusReason2Enum;

$paymentInstrumentUpdateRequest = PaymentInstrumentUpdateRequestBuilder::init()
    ->balanceAccountId('balanceAccountId0')
    ->card(
        CardInfo2Builder::init(
            'brand0',
            'brandVariant8',
            'cardholderName8',
            FormFactor1Enum::PHYSICAL
        )
            ->authentication(
                Authentication1Builder::init()
                    ->email('email8')
                    ->password('password2')
                    ->phone(
                        Phone11Builder::init(
                            'number8',
                            Type410Enum::LANDLINE
                        )->build()
                    )->build()
            )
            ->configuration(
                CardConfiguration2Builder::init(
                    'configurationProfileId6'
                )
                    ->activation('activation2')
                    ->activationUrl('activationUrl8')
                    ->bulkAddress(
                        BulkAddress1Builder::init(
                            'country0'
                        )
                            ->city('city6')
                            ->company('company6')
                            ->email('email0')
                            ->houseNumberOrName('houseNumberOrName4')
                            ->line1('line18')
                            ->build()
                    )
                    ->cardImageId('cardImageId0')
                    ->carrier('carrier8')
                    ->build()
            )
            ->deliveryContact(
                DeliveryContact1Builder::init(
                    StoreLocationBuilder::init(
                        'country0'
                    )
                        ->city('city6')
                        ->line1('line18')
                        ->line2('line20')
                        ->line3('line38')
                        ->postalCode('postalCode8')
                        ->build(),
                    NameBuilder::init(
                        'firstName4',
                        'lastName4'
                    )->build()
                )
                    ->company('company4')
                    ->email('email0')
                    ->fullPhoneNumber('fullPhoneNumber0')
                    ->phoneNumber(
                        ViasPhoneNumberBuilder::init()
                            ->phoneCountryCode('phoneCountryCode8')
                            ->phoneNumber('phoneNumber0')
                            ->phoneType(PhoneTypeEnum::FAX)
                            ->build()
                    )
                    ->webAddress('webAddress4')
                    ->build()
            )
            ->threeDSecure('threeDSecure8')
            ->usage('usage4')
            ->build()
    )
    ->status(Status10Enum::ACTIVE)
    ->statusComment('statusComment8')
    ->statusReason(StatusReason2Enum::EXPIRED)
    ->build();
```

