
# Loyalty Account ID 1

Identification of a Loyalty account.
If loyalty identification of the loyalty account is realised by the Sale System.

## Structure

`LoyaltyAccountID1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entryMode` | [`string(EntryModeEnum)[]`](../../doc/models/entry-mode-enum.md) | Required | Entry mode of the payment instrument information. In the Payment, Loyalty or StoredValue Request messages, it informs the POI System the entry mode of the payment instrument information when read by the Sale Terminal. In the Payment, Loyalty or StoredValue Response messages, it informs the Sale System the entry mode of the payment instrument.<br>Possible values:<br><br>* **Contactless**<br>* **File**<br>* **ICC**<br>* **Keyed**<br>* **MagStripe**<br>* **Manual**<br>* **Mobile**<br>* **RFID**<br>* **Scanned**<br>* **SynchronousICC**<br>* **Tapped** | getEntryMode(): array | setEntryMode(array entryMode): void |
| `identificationType` | [`string(IdentificationType11Enum)`](../../doc/models/identification-type-11-enum.md) | Required | Type of account identification. In a request message, it informs the POI System the type of the account or card identification, when provided by the Sale Terminal. (e.g. because the card information is a barcode read by the Cashier on a scanner device). In a response message, it informs the Sale System the type of the account or card identification.<br>Possible values:<br><br>* **AccountNumber**<br>* **BarCode**<br>* **ISOTrack2**<br>* **PAN**<br>* **PhoneNumber** | getIdentificationType(): string | setIdentificationType(string identificationType): void |
| `identificationSupport` | [`?string(IdentificationSupport1Enum)`](../../doc/models/identification-support-1-enum.md) | Optional | Support of the loyalty account identification. Allows knowing where and how you have found the loyalty account identification.<br>Possible values:<br><br>* **HybridCard**<br>* **LinkedCard**<br>* **LoyaltyCard**<br>* **NoCard** | getIdentificationSupport(): ?string | setIdentificationSupport(?string identificationSupport): void |
| `loyaltyID` | `string` | Required | Loyalty account identification conforming to the IdentificationType. | getLoyaltyID(): string | setLoyaltyID(string loyaltyID): void |

## Example

```php
use AdyenLib\Models\Builders\LoyaltyAccountID1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\IdentificationSupport1Enum;

$loyaltyAccountID1 = LoyaltyAccountID1Builder::init(
    [
        EntryModeEnum::CONTACTLESS,
        EntryModeEnum::TAPPED,
        EntryModeEnum::SYNCHRONOUSICC
    ],
    IdentificationType11Enum::PHONENUMBER,
    'LoyaltyID2'
)
    ->identificationSupport(IdentificationSupport1Enum::NOCARD)
    ->build();
```

