
# Card Configuration 2

Contains information about the configuration profile for your cards. The configuration profile consists of settings required when creating a physical or a virtual card. You identify a configuration profile with its `configurationProfileId`.

When you provide this field in a request, you can override the settings of an existing configuration profile.

Reach out to your Adyen contact to get the values that you can send in this object.

## Structure

`CardConfiguration2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `activation` | `?string` | Optional | The activation label attached to the card that contains the activation instructions.<br><br>This field overrides the activation label design ID defined in the card configuration profile. | getActivation(): ?string | setActivation(?string activation): void |
| `activationUrl` | `?string` | Optional | Your app's URL, if you want to activate cards through your app. For example, **my-app://ref1236a7d**. A QR code is created based on this URL, and is included in the carrier. Before you use this field, reach out to your Adyen contact to set up the QR code process.<br><br>Maximum length: 255 characters.<br><br>**Constraints**: *Maximum Length*: `255` | getActivationUrl(): ?string | setActivationUrl(?string activationUrl): void |
| `bulkAddress` | [`?BulkAddress1`](../../doc/models/bulk-address-1.md) | Optional | Overrides the shipment bulk address defined in the card configuration profile. | getBulkAddress(): ?BulkAddress1 | setBulkAddress(?BulkAddress1 bulkAddress): void |
| `cardImageId` | `?string` | Optional | The unique identifier of the card image. This image is printed on the full front of the card. | getCardImageId(): ?string | setCardImageId(?string cardImageId): void |
| `carrier` | `?string` | Optional | The letter or packaging to which the card is attached.<br><br>This field overrides the carrier design ID defined in the card configuration profile. | getCarrier(): ?string | setCarrier(?string carrier): void |
| `carrierImageId` | `?string` | Optional | The unique identifier of the carrier image. This image is printed on the letter to which the card is attached. | getCarrierImageId(): ?string | setCarrierImageId(?string carrierImageId): void |
| `configurationProfileId` | `string` | Required | The unique identifier of the card configuration profile that contains the settings that are applied to the card. For example, the envelope and PIN mailer designs or the logistics company handling the shipment.<br><br>You can override some of the existing settings in the configuration profile by providing the corresponding fields in the `configuration` object. For example, send the `shipmentMethod` to override the logistics company defined in the card configuration profile. | getConfigurationProfileId(): string | setConfigurationProfileId(string configurationProfileId): void |
| `currency` | `?string` | Optional | The three-letter [ISO-4217](https://en.wikipedia.org/wiki/ISO_4217) currency code of the card. For example, **EUR**.<br><br>This field overrides the existing currency setting on the card configuration profile. | getCurrency(): ?string | setCurrency(?string currency): void |
| `envelope` | `?string` | Optional | Overrides the envelope design ID defined in the card configuration profile. | getEnvelope(): ?string | setEnvelope(?string envelope): void |
| `insert` | `?string` | Optional | Any additional material, such as marketing material, that is shipped together with the card.<br><br>This field overrides the insert design ID defined in the card configuration profile. | getInsert(): ?string | setInsert(?string insert): void |
| `language` | `?string` | Optional | The two-letter [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code of the card. For example, **en**. | getLanguage(): ?string | setLanguage(?string language): void |
| `logoImageId` | `?string` | Optional | The unique identifier of the logo image. This image is printed on the partial front of the card, for example, a logo on the upper right corner. | getLogoImageId(): ?string | setLogoImageId(?string logoImageId): void |
| `pinMailer` | `?string` | Optional | The letter on which the PIN of the card is printed.<br><br>This field overrides the PIN mailer design ID defined in the card configuration profile. | getPinMailer(): ?string | setPinMailer(?string pinMailer): void |
| `printLine` | `?string` | Optional | Print Line.<br><br>Text printed on the physical card below the cardholder name. You provide the value, which can be up to 26 characters. | getPrintLine(): ?string | setPrintLine(?string printLine): void |
| `shipmentMethod` | `?string` | Optional | The logistics company that ships the card.<br><br>This field overrides the logistics company defined in the card configuration profile. | getShipmentMethod(): ?string | setShipmentMethod(?string shipmentMethod): void |

## Example

```php
use AdyenLib\Models\Builders\CardConfiguration2Builder;
use AdyenLib\Models\Builders\BulkAddress1Builder;

$cardConfiguration2 = CardConfiguration2Builder::init(
    'configurationProfileId2'
)
    ->activation('activation2')
    ->activationUrl('activationUrl6')
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
    ->cardImageId('cardImageId4')
    ->carrier('carrier4')
    ->build();
```

