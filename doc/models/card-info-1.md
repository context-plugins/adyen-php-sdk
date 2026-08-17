
# Card Info 1

Contains information about the card. Required when you create a payment instrument of `type` **card**.

## Structure

`CardInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authentication` | [`?Authentication1`](../../doc/models/authentication-1.md) | Optional | Contains the card user's password and mobile phone number. This is required when you issue cards that can be used to make online payments within the EEA and the UK, or can be added to digital wallets. Refer to [3D Secure and digital wallets](https://docs.adyen.com/issuing/3d-secure-and-wallets) for more information. | getAuthentication(): ?Authentication1 | setAuthentication(?Authentication1 authentication): void |
| `brand` | `string` | Required | The brand of the physical or the virtual card.<br>Possible values: **visa**, **mc**. | getBrand(): string | setBrand(string brand): void |
| `brandVariant` | `string` | Required | The brand variant of the physical or the virtual card. For example, **visadebit** or **mcprepaid**.<br><br>> Reach out to your Adyen contact to get the values relevant for your integration. | getBrandVariant(): string | setBrandVariant(string brandVariant): void |
| `cardholderName` | `string` | Required | The name of the cardholder.<br>Maximum length: 26 characters.<br><br>**Constraints**: *Maximum Length*: `26` | getCardholderName(): string | setCardholderName(string cardholderName): void |
| `configuration` | [`?CardConfiguration2`](../../doc/models/card-configuration-2.md) | Optional | Contains information about the configuration profile for your cards. The configuration profile consists of settings required when creating a physical or a virtual card. You identify a configuration profile with its `configurationProfileId`.<br><br>When you provide this field in a request, you can override the settings of an existing configuration profile.<br><br>Reach out to your Adyen contact to get the values that you can send in this object. | getConfiguration(): ?CardConfiguration2 | setConfiguration(?CardConfiguration2 configuration): void |
| `deliveryContact` | [`?DeliveryContact1`](../../doc/models/delivery-contact-1.md) | Optional | The delivery contact (name and address) for physical card delivery. | getDeliveryContact(): ?DeliveryContact1 | setDeliveryContact(?DeliveryContact1 deliveryContact): void |
| `formFactor` | [`string(FormFactor1Enum)`](../../doc/models/form-factor-1-enum.md) | Required | The form factor of the card.<br>Possible values: **virtual**, **physical**. | getFormFactor(): string | setFormFactor(string formFactor): void |
| `threeDSecure` | `?string` | Optional | The 3DS configuration of the physical or the virtual card. Possible values: **fullySupported**, **secureCorporate**.<br><br>> Reach out to your Adyen contact to get the values relevant for your integration. | getThreeDSecure(): ?string | setThreeDSecure(?string threeDSecure): void |
| `usage` | `?string` | Optional | Specifies how many times the card can be used. Possible values: **singleUse**, **multiUse**.<br><br>> Reach out to your Adyen contact to determine the value relevant for your integration. | getUsage(): ?string | setUsage(?string usage): void |

## Example

```php
use AdyenLib\Models\Builders\CardInfo1Builder;
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

$cardInfo1 = CardInfo1Builder::init(
    'brand4',
    'brandVariant2',
    'cardholderName6',
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
    ->threeDSecure('threeDSecure6')
    ->usage('usage8')
    ->build();
```

