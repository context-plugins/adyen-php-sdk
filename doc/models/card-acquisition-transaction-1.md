
# Card Acquisition Transaction 1

Data related to the payment and loyalty card acquisition.

## Structure

`CardAcquisitionTransaction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedPaymentBrand` | `?(string[])` | Optional | Card payment brands allowed by the Sale System for the payment transaction.<br><br>**Constraints**: *Pattern*: `^.+$` | getAllowedPaymentBrand(): ?array | setAllowedPaymentBrand(?array allowedPaymentBrand): void |
| `allowedLoyaltyBrand` | `?(string[])` | Optional | Loyalty brands or programs allowed by the Sale System for the loyalty transaction.<br><br>**Constraints**: *Pattern*: `^.+$` | getAllowedLoyaltyBrand(): ?array | setAllowedLoyaltyBrand(?array allowedLoyaltyBrand): void |
| `loyaltyHandling` | [`?string(LoyaltyHandling2Enum)`](../../doc/models/loyalty-handling-2-enum.md) | Optional | Type of Loyalty processing requested by the Sale System. An way to specify what the POI has to handle concerning the loyalty.<br>Possible values:<br><br>* **Allowed**<br>* **Forbidden**<br>* **Processed**<br>* **Proposed**<br>* **Required** | getLoyaltyHandling(): ?string | setLoyaltyHandling(?string loyaltyHandling): void |
| `customerLanguage` | `?string` | Optional | The language used on the terminal screen or in text printed by the terminal.<br>Typical use case is setting the language on unattended terminals. Format: two-character [ISO 639:2023](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) format.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getCustomerLanguage(): ?string | setCustomerLanguage(?string customerLanguage): void |
| `forceEntryMode` | [`?(string(ForceEntryModeEnum)[])`](../../doc/models/force-entry-mode-enum.md) | Optional | Payment instrument entry mode requested by the Sale System. Avoid retry on an out of order card reading device, when the sale system knows that some card entry modes on the POI do not work.<br>Possible values:<br><br>* **CheckReader**<br>* **Contactless**<br>* **File**<br>* **ICC**<br>* **Keyed**<br>* **MagStripe**<br>* **Manual**<br>* **RFID**<br>* **Scanned**<br>* **SynchronousICC**<br>* **Tapped** | getForceEntryMode(): ?array | setForceEntryMode(?array forceEntryMode): void |
| `forceCustomerSelectionFlag` | `?bool` | Optional | Indicates if the Customer realises the selection of the card application. | getForceCustomerSelectionFlag(): ?bool | setForceCustomerSelectionFlag(?bool forceCustomerSelectionFlag): void |
| `totalAmount` | `?float` | Optional | Amount of a transaction. In the Card Acquisition Request message, it allows the processing of a contactless card.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTotalAmount(): ?float | setTotalAmount(?float totalAmount): void |
| `paymentType` | [`?string(PaymentType1Enum)`](../../doc/models/payment-type-1-enum.md) | Optional | Type of payment transaction. Elements requested by the Sale System that are related to the payment only.<br>Possible values:<br><br>* **CashAdvance**<br>* **CashDeposit**<br>* **Completion**<br>* **FirstReservation**<br>* **Instalment**<br>* **IssuerInstalment**<br>* **Normal**<br>* **OneTimeReservation**<br>* **PaidOut**<br>* **Recurring**<br>* **Refund**<br>* **UpdateReservation** | getPaymentType(): ?string | setPaymentType(?string paymentType): void |
| `cashBackFlag` | `?bool` | Optional | Cash back has been requested with the payment transaction. Allows choice of the Customer language when the POI displays messages or print text to Merchant interface. | getCashBackFlag(): ?bool | setCashBackFlag(?bool cashBackFlag): void |

## Example

```php
use AdyenLib\Models\Builders\CardAcquisitionTransaction1Builder;
use AdyenLib\Models\LoyaltyHandling2Enum;
use AdyenLib\Models\ForceEntryModeEnum;

$cardAcquisitionTransaction1 = CardAcquisitionTransaction1Builder::init()
    ->allowedPaymentBrand(
        [
            'AllowedPaymentBrand4',
            'AllowedPaymentBrand5'
        ]
    )
    ->allowedLoyaltyBrand(
        [
            'AllowedLoyaltyBrand2'
        ]
    )
    ->loyaltyHandling(LoyaltyHandling2Enum::REQUIRED)
    ->customerLanguage('CustomerLanguage6')
    ->forceEntryMode(
        [
            ForceEntryModeEnum::MAGSTRIPE
        ]
    )
    ->build();
```

